---
title: 'Vorgehensweise: Asynchrones Aufrufen eines Webdiensts (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: 01d2fad6be94f23457ba37cbb15521765e0bea17
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376203"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a><span data-ttu-id="d4876-102">Vorgehensweise: Asynchrones Aufrufen eines Webdiensts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4876-102">How to: Call a Web Service Asynchronously (Visual Basic)</span></span>

<span data-ttu-id="d4876-103">Dieses Beispiel hängt einen Handler an das asynchrone Handlerereignis eines Webdiensts an, sodass dieses das Ergebnis eines asynchronen Methodenaufrufs abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="d4876-103">This example attaches a handler to a Web service's asynchronous handler event, so that it can retrieve the result of an asynchronous method call.</span></span> <span data-ttu-id="d4876-104">Dieses Beispiel verwendet den Webdienst DemoTemperatureService unter `http://www.xmethods.net`.</span><span class="sxs-lookup"><span data-stu-id="d4876-104">This example used the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span>

<span data-ttu-id="d4876-105">Wenn Sie im Projekt in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) von Visual Studio auf einen Webdienst verweisen, wird dieser dem `My.WebServices`-Objekt hinzugefügt und die IDE generiert eine Client-Proxyklasse für den Zugriff auf einen festgelegten Webdienst.</span><span class="sxs-lookup"><span data-stu-id="d4876-105">When you reference a Web service in your project in the Visual Studio Integrated Development Environment (IDE), it is added to the `My.WebServices` object, and the IDE generates a client proxy class to access a specified Web service</span></span>

<span data-ttu-id="d4876-106">Mit der Proxyklasse ist es möglich, die Webdienstmethoden synchron aufzurufen, während die Anwendung darauf wartet, dass die Funktion abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d4876-106">The proxy class allows you to call the Web service methods synchronously, where your application waits for the function to complete.</span></span> <span data-ttu-id="d4876-107">Außerdem erstellt das Proxy weitere Member zur asynchronen Unterstütztung der Methode.</span><span class="sxs-lookup"><span data-stu-id="d4876-107">In addition, the proxy creates additional members to help call the method asynchronously.</span></span> <span data-ttu-id="d4876-108">Für jede Webdienstfunktion, *NameOfWebServiceFunction*, erstellt das Proxy eine *NameOfWebServiceFunction*`Async`-Unterroutine, ein *NameOfWebServiceFunction*`Completed`-Ereignis und eine *NameOfWebServiceFunction*`CompletedEventArgs`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d4876-108">For each Web service function, *NameOfWebServiceFunction*, the proxy creates a *NameOfWebServiceFunction*`Async` subroutine, a *NameOfWebServiceFunction*`Completed` event, and a *NameOfWebServiceFunction*`CompletedEventArgs` class.</span></span> <span data-ttu-id="d4876-109">Dieses Beispiel demonstriert, wie Sie die asynchronen Member für den Zugriff auf die `getTemp`-Funktion des Webdiensts DemoTemperatureService verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4876-109">This example demonstrates how to use the asynchronous members to access the `getTemp` function of the DemoTemperatureService Web service.</span></span>

> [!NOTE]
> <span data-ttu-id="d4876-110">Dieser Code funktioniert nicht in Webanwendungen, denn ASP.NET unterstützt nicht das Objekt `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="d4876-110">This code does not work in Web applications, because ASP.NET does not support the `My.WebServices` object.</span></span>

### <a name="to-call-a-web-service-asynchronously"></a><span data-ttu-id="d4876-111">Asynchroner Aufruf eines Webdiensts</span><span class="sxs-lookup"><span data-stu-id="d4876-111">To call a Web service asynchronously</span></span>

1. <span data-ttu-id="d4876-112">Referenzieren Sie den Webdienst DemoTemperatureService unter `http://www.xmethods.net`.</span><span class="sxs-lookup"><span data-stu-id="d4876-112">Reference the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span> <span data-ttu-id="d4876-113">Die Adresse lautet</span><span class="sxs-lookup"><span data-stu-id="d4876-113">The address is</span></span>

    ```
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl
    ```

2. <span data-ttu-id="d4876-114">Fügen Sie einen Ereignishandler für das `getTempCompleted`-Ereignis hinzu:</span><span class="sxs-lookup"><span data-stu-id="d4876-114">Add an event handler for the `getTempCompleted` event:</span></span>

    ```vb
    Private Sub getTempCompletedHandler(ByVal sender As Object,
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)

        MsgBox("Temperature: " & e.Result)
    End Sub
    ```

    > [!NOTE]
    > <span data-ttu-id="d4876-115">Die Anweisung `Handles` lässt sich nicht für das Zuordnen eines Ereignishandlers zu den Ereignissen des `My.WebServices`-Objekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4876-115">You cannot use the `Handles` statement to associate an event handler with the `My.WebServices` object's events.</span></span>

3. <span data-ttu-id="d4876-116">Fügen Sie ein Feld hinzu um nachverfolgen zu können, ob der Ereignishandler dem `getTempCompleted`-Ereignis hinzugefügt wurde:</span><span class="sxs-lookup"><span data-stu-id="d4876-116">Add a field to track if the event handler has been added to the `getTempCompleted` event:</span></span>

    ```vb
    Private handlerAttached As Boolean = False
    ```

4. <span data-ttu-id="d4876-117">Fügen Sie eine Methode hinzu, um den Ereignishandler zum `getTempCompleted`-Ereignis hinzufügen – sofern nötig – und zum Aufruf der `getTempAsync`-Methode:</span><span class="sxs-lookup"><span data-stu-id="d4876-117">Add a method to add the event handler to the `getTempCompleted` event, if necessary, and to call the `getTempAsync` method:</span></span>

    ```vb
    Sub CallGetTempAsync(ByVal zipCode As Integer)
        If Not handlerAttached Then
            AddHandler My.WebServices.
                TemperatureService.getTempCompleted,
                AddressOf Me.TS_getTempCompleted
            handlerAttached = True
        End If
        My.WebServices.TemperatureService.getTempAsync(zipCode)
    End Sub
    ```

    <span data-ttu-id="d4876-118">Für einen asynchronen Aufruf der `getTemp`-Webmethode rufen Sie die `CallGetTempAsync`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d4876-118">To call the `getTemp` Web method asynchronously, call the `CallGetTempAsync` method.</span></span> <span data-ttu-id="d4876-119">Wenn die Webmethode fertig ist, wird ihr Rückgabewert an den `getTempCompletedHandler`-Ereignishandler übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4876-119">When the Web method finishes, its return value is passed to the `getTempCompletedHandler` event handler.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4876-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4876-120">See also</span></span>

- [<span data-ttu-id="d4876-121">Zugreifen auf Anwendungswebdienste</span><span class="sxs-lookup"><span data-stu-id="d4876-121">Accessing Application Web Services</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
- [<span data-ttu-id="d4876-122">My.WebServices-Objekt</span><span class="sxs-lookup"><span data-stu-id="d4876-122">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
