---
title: Fehlervertrag
ms.date: 03/30/2017
ms.assetid: b31b140e-dc3b-408b-b3c7-10b6fe769725
ms.openlocfilehash: 64d02ae6b45cd0e538509d2c7186ac63b9844c14
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840483"
---
# <a name="fault-contract"></a>Fehlervertrag
Im Fehlervertragsbeispiel wird veranschaulicht, wie Fehlerinformationen von einem Dienst zu einem Client übermittelt werden. Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), wurde dabei zusätzlicher Code hinzugefügt, mit dem Dienst um eine interne Ausnahme in einen Fehler zu konvertieren. Der Client versucht, eine Division durch 0 (null) auszuführen, um einen Fehlerzustand beim Dienst zu erzwingen.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Rechnervertrag wurde geändert, um ein <xref:System.ServiceModel.FaultContractAttribute> einzuschließen, wie im folgenden Beispielcode gezeigt.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 Das <xref:System.ServiceModel.FaultContractAttribute>-Attribut gibt an, dass der `Divide`-Vorgang möglicherweise einen Fehler vom Typ `MathFault` zurückgibt. Ein Fehler kann von jedem Typ sein, der serialisiert werden kann. In diesem Fall ist der `MathFault` ein Datenvertrag, wie im Folgenden dargestellt:  
  
```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class MathFault  
{      
    private string operation;  
    private string problemType;  
  
    [DataMember]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]          
    public string ProblemType  
    {  
        get { return problemType; }  
        set { problemType = value; }  
    }  
}  
```  
  
 Die `Divide`-Methode löst eine <xref:System.ServiceModel.FaultException%601>-Ausnahme aus, wenn eine Ausnahme durch Division durch 0 (null) auftritt, wie im folgenden Beispielcode dargestellt. Diese Ausnahme führt dazu, dass ein Fehler an den Client gesendet wird.  
  
```csharp
public int Divide(int n1, int n2)  
{  
    try  
    {  
        return n1 / n2;  
    }  
    catch (DivideByZeroException)  
    {  
        MathFault mf = new MathFault();  
        mf.operation = "division";  
        mf.problemType = "divide by zero";  
        throw new FaultException<MathFault>(mf);  
    }  
}  
```  
  
 Der Clientcode erzwingt einen Fehler, indem eine Division durch 0 (null) angefordert wird. Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Sie sehen, dass die Division durch 0 (null) als Fehler gemeldet wird. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
FaultException<MathFault>: Math fault while doing division. Problem: divide by zero  
  
Press <ENTER> to terminate client.  
```  
  
 Der Client fängt hierzu die entsprechende `FaultException<MathFault>`-Ausnahme ab:  
  
```csharp
catch (FaultException<MathFault> e)  
{  
    Console.WriteLine("FaultException<MathFault>: Math fault while doing " + e.Detail.operation + ". Problem: " + e.Detail.problemType);  
    client.Abort();  
}  
```  
  
 In der Standardeinstellung werden Details zu unerwarteten Ausnahmen nicht an den Client gesendet, damit verhindert wird, dass Informationen zur Dienstimplementierung die sichere Begrenzung des Diensts verlassen. `FaultContract` stellt eine Möglichkeit bereit, um Fehler in einem Vertrag so zu beschreiben und bestimmte Arten von Ausnahmen so zu kennzeichnen, dass sie für die Übertragung an den Client geeignet sind. `FaultException<T>` stellt einen Laufzeitmechanismus zum Senden von Fehlern an den Consumer bereit.  
  
 Es ist jedoch hilfreich, die internen Details eines Dienstfehlers beim Debuggen anzuzeigen. Zum Deaktivieren des oben beschriebenen sicheren Verhaltens können Sie angeben, dass die Details zu allen unbehandelten Ausnahmen auf dem Server in den Fehler eingeschlossen werden sollen, der an den Client gesendet wird. Dies wird durch Festlegen von <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> auf `true` erreicht. Sie können dies im Code festlegen oder in der Konfiguration, wie im folgenden Beispiel gezeigt.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="True" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Darüber hinaus das Verhalten muss mit dem Dienst zugeordneten durch Festlegen der `behaviorConfiguration` Attribut des Diensts in der Konfigurationsdatei auf "calculatorservicebehavior"festgelegt.  
  
 Damit solche Fehler auf dem Client abgefangen werden, muss die nicht generische <xref:System.ServiceModel.FaultException> abgefangen werden.  
  
 Dieses Verhalten sollte nur für Debuggingzwecke verwendet und nie in der Produktion aktiviert werden.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Faults`  
  
