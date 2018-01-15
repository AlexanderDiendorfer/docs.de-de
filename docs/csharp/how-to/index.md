---
title: Artikel zu Vorgehensweisen (C#-Handbuch)
description: Eine Sammlung von einfachen Tipps und kurzen Codebeispielen
author: billwagner
ms.author: wiwagn
ms.date: 12/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 04c780980ef0665b40a0c3a698193fc9fa738424
ms.sourcegitcommit: bf8a3ba647252010bdce86dd914ac6c61b5ba89d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2018
---
# <a name="how-to-c"></a>Vorgehensweise (C#)

Im Abschnitt „Vorgehensweise“ des C#-Handbuchs finden Sie schnelle Antworten zu oft gestellten Fragen. In manchen Fällen können Artikel in mehreren Abschnitten aufgeführt sein. Diese Artikel sollten somit über verschiedene Suchwege einfach zu finden sein. 

## <a name="general-c-concepts"></a>Allgemeine C#-Konzepte

Es gibt einige Tipps und Tricks, die allgemeine C#-Entwicklungsmethoden sind.

- [Initialisieren von Objekten mithilfe eines Objektinitialisierers](../programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md).
- [Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode](../programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md).
- [Verwenden von Lambdaausdrücken](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).
- [Lösen von Namenstypkonflikten durch das Verwenden des globalen Namespacealias](../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).
- [Verwenden der Operatorüberladung](../programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md).
- [Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode](../programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).
- Auch C#-Programmierer sehen einen Nutzen im [Verwenden des `My`-Namespaces aus VB](../programming-guide/namespaces/how-to-use-the-my-namespace.md).
- [Erstellen einer neuen Methode für einen `enum`-Typ mithilfe von Erweiterungsmethoden](../programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

### <a name="class-and-struct-members"></a>Klassen- und Strukturmember

Erstellen Sie Klassen und Strukturen zum implementieren Ihres Programms. Diese Verfahren werden häufig beim Schreiben von Klassen oder Strukturen verwendet.

- [Deklarieren automatisch implementierter Eigenschaften](../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).
- [Deklarieren und Verwenden von Lese-/Schreibeigenschaften](../programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties.md).
- [Definieren von Konstanten](../programming-guide/classes-and-structs/how-to-define-constants.md).
- [Überschreiben der `ToString`-Methode zum Bereitstellen von Zeichenfolgenausgaben](../programming-guide/classes-and-structs/how-to-override-the-tostring-method.md).
- [Definieren von abstrakten Eigenschaften](../programming-guide/classes-and-structs/how-to-define-abstract-properties.md).
- [Verwenden der XML-Dokumentationsfunktionen zum Dokumentieren Ihres Codes](../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md).
- [Explizites Implementieren von Schnittstellenmembern](../programming-guide/interfaces/how-to-explicitly-implement-interface-members.md), um Ihre öffentliche Schnittstelle bündig zu halten.
- [Explizites Implementieren von Membern zweier Schnittstellen](../programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md).

### <a name="working-with-collections"></a>Arbeiten mit Sammlungen

Diese Artikel helfen Ihnen bei der Arbeit mit Datensammlungen.

- [Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md).
- [Zugreifen auf alle Elemente in einer Sammlung mithilfe von `foreach`](../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md).

## <a name="strings"></a>Zeichenfolgen

Zeichenfolgen sind der grundlegende Datentyp für das Anzeigen oder Bearbeiten von Text. Diese Artikel veranschaulichen gängige Vorgehensweisen zu Zeichenfolgen.

- [Vergleichen von Zeichenfolgen](../programming-guide/strings/how-to-compare-strings.md).
- [Ändern des Inhalts einer Zeichenfolge](../programming-guide/strings/how-to-modify-string-contents.md).
- [Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Benutzen von <xref:System.String.Split%2A> zum Trennen von Zeichenfolgen](../programming-guide/strings/how-to-parse-strings-using-string-split.md).
- [Vereinen von mehreren Zeichenfolgen](../programming-guide/strings/how-to-concatenate-multiple-strings.md).
- [Suchen von Text in einer Zeichenfolge](../programming-guide/strings/how-to-search-strings-using-string-methods.md).
- [Suchen von Zeichenfolgen mithilfe von regulären Ausdrücken](../programming-guide/strings/how-to-search-strings-using-regular-expressions.md).

## <a name="convert-between-types"></a>Konvertieren zwischen Typen

Möglicherweise müssen Sie ein Objekt in einen anderen Typ konvertieren.

- [Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Konvertieren zwischen Zeichenfolgen, die einen Hexadezimalwert darstellen, und numerischen Typen](../programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).
- [Konvertieren einer Zeichenfolge in den Wert <xref:System.DateTime>](../programming-guide/strings/how-to-convert-a-string-to-a-datetime.md).
- [Konvertieren eines Bytearrays in einen ganzzahligen Typ](../programming-guide/types/how-to-convert-a-byte-array-to-an-int.md).
- [Konvertieren einer Zeichenfolge in eine Zahl](../programming-guide/types/how-to-convert-a-string-to-a-number.md).
- [Nutzen von `as` und `is` für die sichere Umwandlung in einen anderen Typ](../programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).
- [Definieren von Konvertierungsoperatoren für `struct`-Typen](../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md).
- [Identifizieren, ob ein Typ ein Typ ist, der NULL-Werte zulässt](../programming-guide/nullable-types/how-to-identify-a-nullable-type.md).
- [Konvertieren zwischen Typen, die NULL zulassen, und Typen, die NULL nicht zulassen](../programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).

## <a name="equality-and-ordering-comparisons"></a>Übereinstimmungs- und Reihenfolgenvergleiche

Sie können Typen erstellen, die ihre eigenen Übereinstimmungsregeln, oder eine natürliche Reihenfolge von Objekten ihres Typs definieren.

- [Überprüfen auf Verweisgleichheit](../programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).
- [Definieren von Wertgleichheit für einen Typ](../programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).

## <a name="exception-handling"></a>Ausnahmebehandlung

.NET Programme melden Methoden, die ihre Arbeit nicht erfolgreich abgeschlossen haben, indem sie Ausnahmen auslösen. In den folgenden Artikeln erfahren Sie, wie Sie mit Ausnahmen arbeiten.

- [Behandeln von Ausnahmen mit `try` und `catch`](../programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md).
- [Bereinigen von Ressourcen mit `finally`-Klauseln](../programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md).
- [Abfangen von Nicht-CLS Ausnahmen (Common Language Specification)](../programming-guide/exceptions/how-to-catch-a-non-cls-exception.md).

## <a name="delegates-and-events"></a>Delegaten und Ereignisse

Delegaten und Ereignisse sind Funktionen für Strategien, die lose angeordnete Codeblöcke verwenden.

- [Deklarieren, Instanziieren und Verwenden von Delegaten](../programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md).
- [Kombinieren von Multicastdelegaten](../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md).

Ereignisse sind Funktionen zum Veröffentlichen oder Abonnieren von Benachrichtigungen.

- [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).
- [Implementieren von Schnittstellenereignissen](../programming-guide/events/how-to-implement-interface-events.md).
- [Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen](../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).
- [Auslösen von Basisklassenereignissen in abgeleiteten Klassen](../programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md).
- [Speichern von Ereignisinstanzen in einem Wörterbuch](../programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md).
- [Implementieren von benutzerdefinierten Ereigniszugriffsmethoden](../programming-guide/events/how-to-implement-custom-event-accessors.md).

## <a name="linq-practices"></a>LINQ-Methoden

LINQ ermöglicht Ihnen Code zu schreiben, mit dem Sie Datenquellen abfragen können, die das LINQ-Abfrageausdrucksmuster unterstützen. In den folgenden Artikeln finden Sie Informationen zum Verstehen des Musters, und zum Arbeiten mit verschiedenen Datenquellen.

- [Abfragen einer Auflistung](../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).
- [Verwenden von Lambdaausdrücken in einer Abfrage](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-in-a-query.md).
- [Verwenden von `var` in Abfrageausdrücken](../programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).
- [Zurückgeben von Teilmengen von Elementeigenschaften aus einer Abfrage](../programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).
- [Schreiben von Abfragen mit komplexer Filterung](../programming-guide/concepts/linq/how-to-write-queries-with-complex-filtering.md).
- [Sortieren von Elementen einer Datenquelle](../programming-guide/concepts/linq/how-to-sort-elements.md).
- [Sortieren von Elementen nach mehreren Schlüsseln](../programming-guide/concepts/linq/how-to-sort-elements-on-multiple-keys.md).
- [Steuern des Typs einer Projektion](../programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md).
- [Zählen der Vorkommnisse eines Werts in einer Quellsequenz](../programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md).
- [Berechnen von Zwischenwerten](../programming-guide/concepts/linq/how-to-calculate-intermediate-values.md).
- [Zusammenführen von Daten aus mehreren Quellen](../programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md).
- [Suchen der Unterschiedsmenge zwischen zwei Sequenzen](../programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md).
- [Debuggen von leeren Abfrageergebnissen](../programming-guide/concepts/linq/how-to-debug-empty-query-results-sets.md).
- [Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen](../programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md).

## <a name="multiple-threads-and-async-processing"></a>Mehrere Threads und asynchrone Verarbeitung

Moderne Programme verwenden häufig asynchrone Vorgänge. In den folgenden Artikeln erfahren Sie, wie Sie mit diesen Methoden arbeiten.

- [Verbessern der asynchronen Leistung mit `System.Threading.Tasks.Task.WhenAll`](../programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).
- [Paralleles Erstellen mehrerer Webanforderungen mit `async` und `await`](../programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md).
- [Verwenden von Threadpools](../programming-guide/concepts/threading/how-to-use-a-thread-pool.md).

## <a name="command-line-args-to-your-program"></a>Befehlszeilenargumente für Ihr Programm

C#-Programme haben in der Regel Befehlszeilenargumente. In den folgenden Artikeln erfahren Sie, wie Sie auf Befehlszeilenargumente zugreifen und sie verarbeiten.

- [Abrufen aller Befehlszeilenargumente mit `for`](../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md).
- [Abrufen aller Befehlszeilenargumente mit `foreach`](../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md).