---
title: Objektorientierte Programmierung (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 058d8b932e50f784d4a5cefa9fadfb31953687f0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153922"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="0f6a9-102">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f6a9-102">Object-oriented programming (Visual Basic)</span></span>

<span data-ttu-id="0f6a9-103">Visual Basic bietet vollständige Unterstützung für objektorientierte Programmierung einschließlich Kapselung, Vererbung und Polymorphie.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

 <span data-ttu-id="0f6a9-104">*Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

 <span data-ttu-id="0f6a9-105">*Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

 <span data-ttu-id="0f6a9-106">*Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

 <span data-ttu-id="0f6a9-107">In diesem Abschnitt werden die folgenden Konzepte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="0f6a9-108">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="0f6a9-108">Classes and objects</span></span>](#classes-and-objects)
  - [<span data-ttu-id="0f6a9-109">Class members (Klassenmember)</span><span class="sxs-lookup"><span data-stu-id="0f6a9-109">Class members</span></span>](#class-members)
    - [<span data-ttu-id="0f6a9-110">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="0f6a9-110">Properties and fields</span></span>](#properties-and-fields)
    - [<span data-ttu-id="0f6a9-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="0f6a9-111">Methods</span></span>](#methods)
    - [<span data-ttu-id="0f6a9-112">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="0f6a9-112">Constructors</span></span>](#constructors)
    - [<span data-ttu-id="0f6a9-113">Destruktoren</span><span class="sxs-lookup"><span data-stu-id="0f6a9-113">Destructors</span></span>](#destructors)
    - [<span data-ttu-id="0f6a9-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0f6a9-114">Events</span></span>](#events)
    - [<span data-ttu-id="0f6a9-115">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-115">Nested classes</span></span>](#nested-classes)
  - [<span data-ttu-id="0f6a9-116">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)
    - [<span data-ttu-id="0f6a9-117">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-117">Instantiating classes</span></span>](#instantiating-classes)
    - [<span data-ttu-id="0f6a9-118">Gemeinsam verwendete Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="0f6a9-118">Shared classes and members</span></span>](#shared-classes-and-members)
    - [<span data-ttu-id="0f6a9-119">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-119">Anonymous types</span></span>](#anonymous-types)
- [<span data-ttu-id="0f6a9-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-120">Inheritance</span></span>](#inheritance)
  - [<span data-ttu-id="0f6a9-121">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="0f6a9-121">Overriding members</span></span>](#overriding-members)
- [<span data-ttu-id="0f6a9-122">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-122">Interfaces</span></span>](#interfaces)
- [<span data-ttu-id="0f6a9-123">Generika</span><span class="sxs-lookup"><span data-stu-id="0f6a9-123">Generics</span></span>](#generics)
- [<span data-ttu-id="0f6a9-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="0f6a9-124">Delegates</span></span>](#delegates)

## <a name="classes-and-objects"></a><span data-ttu-id="0f6a9-125">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="0f6a9-125">Classes and objects</span></span>

<span data-ttu-id="0f6a9-126">Die Begriffe *Klasse* und *Objekt* werden manchmal synonym verwendet; genau genommen beschreiben Klassen jedoch den *Typ* von Objekten, während Objekte verwendbare *Instanzen* von Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="0f6a9-127">Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="0f6a9-128">Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="0f6a9-129">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="0f6a9-129">To define a class:</span></span>

```vb
Class SampleClass
End Class
```

<span data-ttu-id="0f6a9-130">Visual Basic bietet auch eine light-Version von Klassen *Strukturen* , sind nützlich, wenn müssen Sie ein großes Objektarray erstellen und möchten nicht zu viel Arbeitsspeicher belegen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="0f6a9-131">So definieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="0f6a9-131">To define a structure:</span></span>

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="0f6a9-132">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-132">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-133">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="0f6a9-134">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="0f6a9-135">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="0f6a9-135">Class members</span></span>

<span data-ttu-id="0f6a9-136">Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="0f6a9-137">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="0f6a9-137">Properties and fields</span></span>

<span data-ttu-id="0f6a9-138">Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="0f6a9-139">Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="0f6a9-140">So definieren Sie ein Feld</span><span class="sxs-lookup"><span data-stu-id="0f6a9-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="0f6a9-141">Eigenschaften verfügen über Get- und Set-Prozeduren, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="0f6a9-142">Visual Basic können Sie entweder ein privates Feld zum Speichern von den Wert der Eigenschaft erstellen, oder verwenden Sie die so genannte automatisch implementierte Eigenschaften, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaftenprozeduren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="0f6a9-143">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0f6a9-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="0f6a9-144">Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

<span data-ttu-id="0f6a9-145">Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="0f6a9-146">Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="0f6a9-147">In Visual Basic können Sie das `ReadOnly`-Schlüsselwort und das `WriteOnly`-Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="0f6a9-148">Automatisch implementierte Eigenschaften können jedoch nicht schreib- oder lesegeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="0f6a9-149">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-149">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-150">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="0f6a9-151">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="0f6a9-152">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="0f6a9-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="0f6a9-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="0f6a9-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="0f6a9-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a><span data-ttu-id="0f6a9-155">Methoden</span><span class="sxs-lookup"><span data-stu-id="0f6a9-155">Methods</span></span>

 <span data-ttu-id="0f6a9-156">Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-156">A *method* is an action that an object can perform.</span></span>

> [!NOTE]
> <span data-ttu-id="0f6a9-157">In Visual Basic gibt es zwei Möglichkeiten, eine Methode zu erstellen: Wenn die Methode keinen Wert zurückgibt, wird die `Sub`-Anweisung verwendet; andernfalls wird die `Function`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="0f6a9-158">So definieren Sie eine Methode einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="0f6a9-159">Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="0f6a9-160">So überladen Sie eine Methode</span><span class="sxs-lookup"><span data-stu-id="0f6a9-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="0f6a9-161">In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="0f6a9-162">Visual Basic unterstützt jedoch auch *Erweiterungsmethoden* , mit denen Sie einer vorhandenen Klasse außerhalb der Klasse der eigentlichen Klassendefinition Methoden hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="0f6a9-163">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-163">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-164">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="0f6a9-165">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="0f6a9-166">Overloads</span><span class="sxs-lookup"><span data-stu-id="0f6a9-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="0f6a9-167">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="0f6a9-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="0f6a9-168">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="0f6a9-168">Constructors</span></span>

<span data-ttu-id="0f6a9-169">Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="0f6a9-170">Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="0f6a9-171">Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="0f6a9-172">Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="0f6a9-173">Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="0f6a9-174">So definieren Sie einen Konstruktor für eine Klasse:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

<span data-ttu-id="0f6a9-175">Weitere Informationen finden Sie unter: [Objektlebensdauer: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="0f6a9-176">Destruktoren</span><span class="sxs-lookup"><span data-stu-id="0f6a9-176">Destructors</span></span>

<span data-ttu-id="0f6a9-177">Destruktoren werden zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="0f6a9-178">In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="0f6a9-179">Möglicherweise sind jedoch noch Destruktoren erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="0f6a9-180">Es kann nur einen Destruktor für eine Klasse geben.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="0f6a9-181">Weitere Informationen zu Destruktoren und der Garbage Collection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="0f6a9-182">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0f6a9-182">Events</span></span>

<span data-ttu-id="0f6a9-183">Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="0f6a9-184">Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="0f6a9-185">Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="0f6a9-186">Um Ereignisse zu deklarieren, verwenden die [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="0f6a9-187">Um Ereignisse auszulösen, verwenden Sie die [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="0f6a9-188">Um Ereignishandler per Deklaration festzulegen, verwenden Sie die [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) Anweisung und die [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="0f6a9-189">Damit können dynamisch hinzufügen, entfernen und ändern den Ereignishandler einem Ereignis zugeordneten, verwenden die [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md) und [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md) zusammen mit den [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="0f6a9-190">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-190">Nested classes</span></span>

<span data-ttu-id="0f6a9-191">Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="0f6a9-192">Standardmäßig ist die geschachtelte Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="0f6a9-193">Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="0f6a9-194">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-194">Access modifiers and access levels</span></span>

<span data-ttu-id="0f6a9-195">Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="0f6a9-196">Die folgenden Zugriffsmodifizierer sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="0f6a9-197">Visual Basic-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="0f6a9-197">Visual Basic Modifier</span></span>|<span data-ttu-id="0f6a9-198">Definition</span><span class="sxs-lookup"><span data-stu-id="0f6a9-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="0f6a9-199">Public</span><span class="sxs-lookup"><span data-stu-id="0f6a9-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="0f6a9-200">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="0f6a9-201">Private</span><span class="sxs-lookup"><span data-stu-id="0f6a9-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="0f6a9-202">Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="0f6a9-203">Protected</span><span class="sxs-lookup"><span data-stu-id="0f6a9-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="0f6a9-204">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="0f6a9-205">Friend</span><span class="sxs-lookup"><span data-stu-id="0f6a9-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="0f6a9-206">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="0f6a9-207">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="0f6a9-208">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-208">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="0f6a9-209">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-209">Instantiating classes</span></span>

<span data-ttu-id="0f6a9-210">Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="0f6a9-211">Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="0f6a9-212">Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="0f6a9-213">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-213">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-214">New-Operator</span><span class="sxs-lookup"><span data-stu-id="0f6a9-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="0f6a9-215">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a><span data-ttu-id="0f6a9-216">Gemeinsam verwendete Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="0f6a9-216">Shared classes and members</span></span>

 <span data-ttu-id="0f6a9-217">Ein freigegebener Member der Klasse ist eine Eigenschaft, Prozedur oder Feld, das von allen Instanzen einer Klasse gemeinsam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

 <span data-ttu-id="0f6a9-218">So definieren Sie einen freigegebenen Member:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-218">To define a shared member:</span></span>

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 <span data-ttu-id="0f6a9-219">Verwenden Sie den Namen der Klasse für den Zugriff auf den freigegebenen Member, ohne ein Objekt dieser Klasse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>

```vb
MsgBox(SampleClass.SampleString)
```

 <span data-ttu-id="0f6a9-220">Freigegebene Module in Visual Basic nur Member freigegeben haben, und können nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="0f6a9-221">Freigegebene Member können nicht auch nicht freigegebene Eigenschaften, Felder oder Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-221">Shared members also cannot access non-shared properties, fields or methods</span></span>

 <span data-ttu-id="0f6a9-222">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-222">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-223">Shared</span><span class="sxs-lookup"><span data-stu-id="0f6a9-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="0f6a9-224">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a><span data-ttu-id="0f6a9-225">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-225">Anonymous types</span></span>

<span data-ttu-id="0f6a9-226">Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="0f6a9-227">Stattdessen erzeugt der Compiler eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="0f6a9-228">Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="0f6a9-229">So erstellen Sie eine Instanz eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="0f6a9-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="0f6a9-230">Weitere Informationen finden Sie unter: [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="0f6a9-231">Vererbung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-231">Inheritance</span></span>

<span data-ttu-id="0f6a9-232">Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="0f6a9-233">Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="0f6a9-234">Alle Klassen in Visual Basic erben jedoch implizit von der <xref:System.Object> -Klasse, die .NET-Klassenhierarchie unterstützt und Low-Level-Dienste für alle Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="0f6a9-235">Visual Basic unterstützt keine mehrfachvererbung.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="0f6a9-236">Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="0f6a9-237">So erben Sie von einer Basisklasse</span><span class="sxs-lookup"><span data-stu-id="0f6a9-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="0f6a9-238">Standardmäßig können alle Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-238">By default all classes can be inherited.</span></span> <span data-ttu-id="0f6a9-239">Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="0f6a9-240">So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="0f6a9-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="0f6a9-241">So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="0f6a9-242">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-242">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-243">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="0f6a9-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="0f6a9-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="0f6a9-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="0f6a9-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="0f6a9-246">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="0f6a9-246">Overriding members</span></span>

<span data-ttu-id="0f6a9-247">Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="0f6a9-248">Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="0f6a9-249">Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="0f6a9-250">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="0f6a9-251">Visual Basic-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="0f6a9-251">Visual Basic Modifier</span></span>|<span data-ttu-id="0f6a9-252">Definition</span><span class="sxs-lookup"><span data-stu-id="0f6a9-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="0f6a9-253">Overridable</span><span class="sxs-lookup"><span data-stu-id="0f6a9-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="0f6a9-254">Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="0f6a9-255">Overrides</span><span class="sxs-lookup"><span data-stu-id="0f6a9-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="0f6a9-256">Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="0f6a9-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="0f6a9-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="0f6a9-258">Verhindert das Überschreiben eines Members in einer erbenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="0f6a9-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="0f6a9-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="0f6a9-260">Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="0f6a9-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="0f6a9-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="0f6a9-262">Blendet einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="0f6a9-263">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-263">Interfaces</span></span>

<span data-ttu-id="0f6a9-264">Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="0f6a9-265">Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="0f6a9-266">Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="0f6a9-267">Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="0f6a9-268">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f6a9-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="0f6a9-269">So implementieren Sie eine Schnittstelle in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="0f6a9-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="0f6a9-270">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-270">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-271">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0f6a9-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="0f6a9-272">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="0f6a9-273">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a><span data-ttu-id="0f6a9-274">Generics</span><span class="sxs-lookup"><span data-stu-id="0f6a9-274">Generics</span></span>

<span data-ttu-id="0f6a9-275">Klassen, Strukturen, Schnittstellen und Methoden in .NET zählen *Typparameter* , definieren die Typen von Objekten, die sie speichern oder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="0f6a9-276">Das einfachste Beispiel für Generics ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="0f6a9-277">So definieren Sie eine generische Klasse</span><span class="sxs-lookup"><span data-stu-id="0f6a9-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="0f6a9-278">So erstellen Sie eine Instanz einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="0f6a9-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="0f6a9-279">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-279">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-280">Generika</span><span class="sxs-lookup"><span data-stu-id="0f6a9-280">Generics</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="0f6a9-281">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f6a9-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="0f6a9-282">Delegaten</span><span class="sxs-lookup"><span data-stu-id="0f6a9-282">Delegates</span></span>

 <span data-ttu-id="0f6a9-283">Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="0f6a9-284">Sie können die Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="0f6a9-285">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="0f6a9-286">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0f6a9-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="0f6a9-287">Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="0f6a9-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="0f6a9-288">So erstellen Sie einen Delegaten</span><span class="sxs-lookup"><span data-stu-id="0f6a9-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="0f6a9-289">So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

<span data-ttu-id="0f6a9-290">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0f6a9-290">For more information, see:</span></span>

- [<span data-ttu-id="0f6a9-291">Delegaten</span><span class="sxs-lookup"><span data-stu-id="0f6a9-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="0f6a9-292">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f6a9-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="0f6a9-293">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="0f6a9-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="0f6a9-294">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f6a9-294">See also</span></span>

- [<span data-ttu-id="0f6a9-295">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0f6a9-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
