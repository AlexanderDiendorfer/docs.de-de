---
title: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 73633c2c6119204f2fb608b32ae794a2e07b27d0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747073"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts

Dies ist die Dritte von sechs Aufgaben, die zum Erstellen einer WCF-Anwendung erforderlich sind. Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](getting-started-tutorial.md).

In diesem Artikel wird beschrieben, wie ein WCF-Dienst in einer Konsolenanwendung gehostet wird. Dieses Verfahren umfasst die folgenden Schritte:

- Erstellen eines Konsolenanwendungsprojekts zum Hosten des Diensts

- Erstellen eines Diensthosts für den Dienst

- Aktivieren des Metadatenaustauschs

- Öffnen des Diensthosts

Eine vollständige Liste des für diese Aufgabe geschriebenen Codes wird in einem Beispiel im Anschluss an das Verfahren bereitgestellt.

## <a name="create-a-new-console-application-to-host-the-service"></a>Erstellen Sie eine neue Konsolenanwendung zum Hosten des Diensts

1. Erstellen Sie ein neues Konsolenanwendungsprojekt in Visual Studio, indem Sie mit der rechten Maustaste auf die Projektmappe mit ersten Schritten und auswählen **hinzufügen** > **neues Projekt**. In der **neues Projekt hinzufügen** im Dialogfeld auf der linken Seite, und wählen die **Windows Desktop** unter Kategorie **Visual C#-** oder **Visual Basic**. Wählen Sie die **Konsolen-App ((.NET Framework)** Vorlage, und nennen Sie das Projekt **GettingStartedHost**.

2. Fügen Sie dem GettingStartedHost-Projekt einen Verweis auf das GettingStartedLib-Projekt hinzu. Mit der rechten Maustaste auf die **Verweise** Ordner unterhalb des GettingStartedHost-Projekts in **Projektmappen-Explorer**, und wählen Sie dann **Verweis hinzufügen**. In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Lösung** klicken Sie auf der linken Seite des Dialogfelds, wählen Sie im mittleren Abschnitt des Dialogfelds GettingStartedLib, und wählen Sie dann **hinzufügen**. Dadurch werden die in GettingStartedLib definierten Typen für das GettingStartedHost-Projekt verfügbar.

3. Fügen Sie dem GettingStartedHost-Projekt einen Verweis auf den System.ServiceModel hinzu. Mit der rechten Maustaste die **Verweise** Ordner unterhalb des GettingStartedHost-Projekts in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen**. In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Framework** auf der linken Seite des Dialogfelds unter **Assemblys**. Suchen und auswählen **System.ServiceModel**, und wählen Sie dann **OK**. Speichern Sie die Projektmappe durch Auswahl **Datei** > **Alles speichern**.

## <a name="host-the-service"></a>Hosten des Diensts

Öffnen Sie die Datei Program.cs oder Module.vb, und geben Sie den folgenden Code ein:

```csharp
using System;
using System.ServiceModel;
using System.ServiceModel.Description;
using GettingStartedLib;

namespace GettingStartedHost
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 1 Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 Create a ServiceHost instance
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 Start the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
                selfHost.Close();
            }
            catch (CommunicationException ce)
            {
                Console.WriteLine("An exception occurred: {0}", ce.Message);
                selfHost.Abort();
            }
        }
    }
}
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted")

            ' Step 2 Create a ServiceHost instance
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
           Try

                ' Step 3 Add a service endpoint
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 Enable metadata exchange.
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 Start the service
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

**Schritt 1** -erstellt eine Instanz der Uri-Klasse, die die Basisadresse des Diensts enthalten soll. Dienste werden über eine URL identifiziert, die eine Basisadresse und einen optionalen URI enthält. Die Basisadresse ist wie folgt formatiert: [Transport]://[Computername oder Domäne][:optionaler Port #]/[optionales URI-Segment]. Für die Basisadresse des Rechnerdiensts werden HTTP-Transport, localhost, Port 8000 und das URI-Segment „GettingStarted“ verwendet.

**Schritt 2** – erstellt eine Instanz der <xref:System.ServiceModel.ServiceHost> Klasse, um den Dienst zu hosten. Der Konstruktor akzeptiert zwei Parameter: den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Diensts.

**Schritt 3** – erstellt eine <xref:System.ServiceModel.Description.ServiceEndpoint> Instanz. Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen. Der <xref:System.ServiceModel.Description.ServiceEndpoint>-Konstruktor akzeptiert daher den Schnittstellentyp des Dienstvertrags, eine Bindung und eine Adresse. Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren. Die in diesem Beispiel verwendete Bindung ist <xref:System.ServiceModel.WSHttpBinding>. Dies ist eine integrierte Bindung, die für die Verbindung mit Endpunkten verwendet wird, die den WS-*-Spezifikationen entsprechen. Weitere Informationen zu WCF-Bindungen finden Sie unter [WCF Bindings Overview (Übersicht über WCF-Bindungen)](bindings-overview.md). Die Adresse wird an die Basisadresse angefügt, um den Endpunkt zu identifizieren. In diesem Code angegebene Adresse ist "CalculatorService", daher ist die vollqualifizierte Adresse für den Endpunkt `"http://localhost:8000/GettingStarted/CalculatorService"`.

> [!IMPORTANT]
> Das Hinzufügen eines Dienstendpunkts ist optional, wenn .NET Framework 4 oder höher verwendet wird. Wenn im Code oder in der Konfiguration keine Endpunkte hinzugefügt wurden, fügt WCF in diesen Versionen einen Standardendpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wurden. Weitere Informationen zu Standardendpunkten finden Sie unter [Specifying an Endpoint Address (Angeben einer Endpunktadresse)](specifying-an-endpoint-address.md). Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](./samples/simplified-configuration-for-wcf-services.md).

**Schritt 4** – Aktivieren des Metadatenaustauschs. Clients verwenden den Metadatenaustausch, um Proxys zu generieren, die zum Aufrufen von Dienstvorgängen verwendet werden. Zum Aktivieren von Metadatenaustausch erstellen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz, legen ihre <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` fest und fügen der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>-Instanz das Verhalten der <xref:System.ServiceModel.ServiceHost>-Auflistung hinzu.

**Schritt 5** : Öffnen der <xref:System.ServiceModel.ServiceHost> zum Lauschen auf eingehender Nachrichten. Der Code wartet darauf, dass der Benutzer die EINGABETASTE drückt. Wenn dies nicht erfolgt, wird die App sofort geschlossen und der Dienst heruntergefahren. Beachten Sie auch, dass ein try/catch-Block verwendet wird. Nachdem der <xref:System.ServiceModel.ServiceHost> instanziiert wurde, wird der gesamte sonstige Code in einen try/catch-Block eingefügt. Weitere Informationen zum sicheren Abfangen von Ausnahmen durch <xref:System.ServiceModel.ServiceHost>, finden Sie unter [verwenden schließen "und" Abort, WCF-Client-Ressourcen freizugeben.](samples/use-close-abort-release-wcf-client-resources.md)

> [!IMPORTANT]
> Wenn Sie einen WCF-Dienstbibliothek hinzufügen, kann Visual Studio hostet es für Sie beim Debuggen von einem Diensthost ab. Um Konflikte zu vermeiden, können Sie diese deaktivieren. 
> 1. Öffnen der Projekteigenschaften für GettingStartedLib.
> 2. Wechseln Sie zu **WCF-Optionen** , und deaktivieren Sie **starten WCF-Diensthost beim Debuggen**.

## <a name="verify-the-service-is-working"></a>Stellen Sie sicher, dass der Dienst funktioniert.

1. Führen Sie die GettingStartedHost-Konsole Anwendung von innerhalb von Visual Studio.

   Der Dienst muss mit Administratorrechten ausgeführt werden. Da Visual Studio mit Administratorrechten geöffnet wurde, wird die GettingStartedHost auch mit Administratorrechten ausgeführt. Sie können auch öffnen, eine neue Eingabeaufforderung mit **als Administrator ausführen** und führen Sie service.exe darin.

2. Öffnen Sie einen Webbrowser, und navigieren Sie zu den Dienst Debuggen-Seite unter `http://localhost:8000/GettingStarted/`. **Hinweis! Es ist wichtig, Schrägstrich enden.**

## <a name="example"></a>Beispiel

Das folgende Beispiel enthält den Dienstvertrag und die Implementierung aus den vorangegangenen Schritten im Lernprogramm und hostet den Dienst in einer Konsolenanwendung.

Um dies mit einem Befehlszeilencompiler kompilieren, kompilieren Sie IService1.cs und Service1.cs in eine Klassenbibliothek, die verweist `System.ServiceModel.dll`. Kompilieren Sie "Program.cs", als eine Konsolenanwendung.

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
        public interface ICalculator
        {
            [OperationContract]
            double Add(double n1, double n2);
            [OperationContract]
            double Subtract(double n1, double n2);
            [OperationContract]
            double Multiply(double n1, double n2);
            [OperationContract]
            double Divide(double n1, double n2);
        }
}
```

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```csharp
using System;
using System.ServiceModel;
using System.ServiceModel.Description;
using GettingStartedLib;

namespace GettingStartedHost
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 of the hosting procedure: Create ServiceHost
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 of the hosting procedure: Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 of the hosting procedure: Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
                selfHost.Close();
            }
            catch (CommunicationException ce)
            {
                Console.WriteLine("An exception occurred: {0}", ce.Message);
                selfHost.Abort();
            }
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

            ' Step 2 of the hosting procedure: Create ServiceHost
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
            Try

                ' Step 3 of the hosting procedure: Add a service endpoint.
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 of the hosting procedure: Enable metadata exchange.
                ' Enable metadata exchange
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

> [!NOTE]
> Dienste wie dieser müssen dazu berechtigt sein, HTTP-Adressen auf dem Computer zum Überwachen zu registrieren. Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden. Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](feature-details/configuring-http-and-https.md). Wird der Dienst unter Visual Studio ausgeführt, muss „service.exe“ mit Administratorrechten ausgeführt werden.

## <a name="next-steps"></a>Nächste Schritte

Der Dienst wird nun ausgeführt. In der nächsten Aufgabe erstellen Sie einen WCF-Client.

> [!div class="nextstepaction"]
> [Vorgehensweise: Erstellen Sie einen WCF-client](how-to-create-a-wcf-client.md)

Informationen zur Problembehandlung finden Sie unter [Troubleshooting the Getting Started Tutorial (Problembehandlung für das Tutorial „Erste Schritte“)](troubleshooting-the-getting-started-tutorial.md).

## <a name="see-also"></a>Siehe auch

- [Erste Schritte](samples/getting-started-sample.md)
- [Selbst gehostete Dienste](samples/self-host.md)
- [Hosting-Dienste](hosting-services.md)
