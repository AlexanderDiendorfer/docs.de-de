---
title: Bereitstellen der Funktionen für NetDataContractSerializer mit DataContractSerializer und DataContractResolver
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: 481d9d7f30f9c2137ec91a87c9743dcb0a97baf7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816808"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a>Bereitstellen der Funktionen für NetDataContractSerializer mit DataContractSerializer und DataContractResolver
In diesem Beispiel wird veranschaulicht, wie die Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> mit einem entsprechenden <xref:System.Runtime.Serialization.DataContractResolver> die gleiche Funktionalität wie der <xref:System.Runtime.Serialization.NetDataContractSerializer> bereitstellt. In diesem Beispiel wird gezeigt, wie der entsprechende <xref:System.Runtime.Serialization.DataContractResolver> erstellt und dem <xref:System.Runtime.Serialization.DataContractSerializer> hinzugefügt wird.

## <a name="sample-details"></a>Beispieldetails
 <xref:System.Runtime.Serialization.NetDataContractSerializer> unterscheidet sich von <xref:System.Runtime.Serialization.DataContractSerializer> in einem wichtigen Punkt: <xref:System.Runtime.Serialization.NetDataContractSerializer> enthält im Gegensatz zu <xref:System.Runtime.Serialization.DataContractSerializer> CLR-Typinformationen im serialisierten XML. <xref:System.Runtime.Serialization.NetDataContractSerializer> kann daher nur verwendet werden, wenn sowohl der Endpunkt für die Serialisierung als auch der Endpunkt für die Deserialisierung den gleichen CLR-Typ aufweisen. Es wird jedoch empfohlen, <xref:System.Runtime.Serialization.DataContractSerializer> zu verwenden, da er eine höhere Leistung bietet als <xref:System.Runtime.Serialization.NetDataContractSerializer>. Sie können die Informationen ändern, die in <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert sind, indem Sie einen <xref:System.Runtime.Serialization.DataContractResolver> hinzuzufügen.

 Dieses Beispiel besteht aus zwei Projekten. Das erste Projekt verwendet <xref:System.Runtime.Serialization.NetDataContractSerializer> für das Serialisieren eines Objekts. Das zweite Projekt verwendet <xref:System.Runtime.Serialization.DataContractSerializer> mit einem <xref:System.Runtime.Serialization.DataContractResolver>, um die gleiche Funktionalität wie das erste Projekt bereitzustellen.

 Im folgenden Codebeispiel wird die Implementierung von einem benutzerdefinierten <xref:System.Runtime.Serialization.DataContractResolver> mit dem Namen `MyDataContractResolver` veranschaulicht, der dem <xref:System.Runtime.Serialization.DataContractSerializer> im DCSwithDCR-Projekt hinzugefügt wird.

```csharp
class MyDataContractResolver : DataContractResolver
{
    private XmlDictionary dictionary = new XmlDictionary();

    public MyDataContractResolver()
    {
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);
        if (type == null)
        {
            type = Type.GetType(typeName + ", " + typeNamespace);
        }
        return type;
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);
        if (typeName == null || typeNamespace == null)
        {
            XmlDictionary dictionary = new XmlDictionary();
            typeName = dictionary.Add(dataContractType.FullName);
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);
        }
    }
}
```

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1.  Öffnen Sie die Projektmappendatei dcrsample.sln mit Visual Studio 2012.

2.  Mit der rechten Maustaste in der Projektmappendatei, und wählen Sie **Eigenschaften**.

3.  In der **Eigenschaftenseiten für Projektmappen** Dialogfeld unter **allgemeine Eigenschaften**, **Startprojekt**Option **mehrere Startprojekte:**.

4.  Neben der **DCSwithDCR** -Projekt, wählen **starten** aus der **Aktion** Dropdownliste.

5.  Neben der **NetDCS** -Projekt, wählen **starten** aus der **Aktion** Dropdownliste.

6.  Klicken Sie auf **OK** um das Dialogfeld zu schließen.

7.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

8.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
  
