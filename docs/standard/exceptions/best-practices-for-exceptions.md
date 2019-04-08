---
title: Best Practices für Ausnahmen – .NET
ms.date: 12/05/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 6c979483497ff640be7d1126d63ce95130f6c02b
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58633750"
---
# <a name="best-practices-for-exceptions"></a>Bewährte Methoden für Ausnahmen

Eine ausgereifte App behandelt Ausnahmen und Fehler, um App-Abstürze zu verhindern. In diesem Abschnitt werden bewährte Methoden für die Behandlung und Erstellung von Ausnahmen beschrieben.

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a>Verwenden Sie Try/Catch/Final-Blöcke zum Beheben von Fehlern oder zum Freigeben von Ressourcen.

Betten Sie Code, der Ausnahmen erzeugen kann, in `try`/`catch`-Blöcke ein, ***damit*** ihr Code nach diesen Ausnahmen wiederhergestellt werden kann. Ordnen Sie Ausnahmen in `catch`-Blöcken immer von der am stärksten abgeleiteten bis zur am wenigsten abgeleiteten. Alle Ausnahmen werden von <xref:System.Exception> abgeleitet. Stärker abgeleitete Ausnahmen werden nicht durch eine Catch-Klausel verarbeitet, der eine Catch-Klausel für eine Basisausnahmeklasse vorangestellt ist. Wenn Ihr Code nicht aus einer Ausnahme wiederhergestellt werden kann, erfassen Sie diese Ausnahme nicht. Aktivieren Sie Methoden weiter oben in der Aufrufliste, um nach Möglichkeit eine Wiederherstellung auszuführen.

Bereinigen Sie die Ressourcen, die mit `using`-Anweisungen oder `finally`-Blöcken zugeordnet wurden. Bevorzugen Sie `using`-Anweisungen, um Ressourcen automatisch zu bereinigen, wenn Ausnahmen ausgelöst werden. Verwenden Sie `finally`-Blöcke, um Ressourcen zu bereinigen, die <xref:System.IDisposable> nicht implementieren. Code in einer `finally`-Klausel wird fast immer ausgeführt – auch wenn Ausnahmen ausgelöst werden.

## <a name="handle-common-conditions-without-throwing-exceptions"></a>Behandeln von allgemeinen Bedingungen ohne Auslösen von Ausnahmen

Bedingungen, deren Auftreten wahrscheinlich ist, die aber eine Ausnahme auslösen, sollten Sie so behandeln, dass die Ausnahme vermieden wird. Wenn Sie z.B. versuchen, eine bereits geschlossene Verbindung zu schließen, erhalten Sie eine `InvalidOperationException`. Dies können Sie verhindern, indem Sie eine `if`-Anweisung verwenden, um den Verbindungsstatus zu überprüfen, bevor Sie versuchen, die Verbindung zu schließen.

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

Wenn Sie den Verbindungsstatus vor dem Schließen der Verbindung nicht überprüfen, können Sie eine `InvalidOperationException`-Ausnahme abfangen.

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

Die Wahl der Methode hängt von der erwarteten Häufigkeit des Ereignisses ab.

- Verwenden Sie die Ausnahmebehandlung, wenn das Ereignis nicht sehr häufig auftritt, d. h. wenn das Ereignis wirklich außergewöhnlich ist und auf einen Fehler hinweist (z. B. ein unerwartetes Dateiende). Wenn Sie die Ausnahmebehandlung verwenden, wird weniger Code in normalen Bedingungen ausgeführt.

- Wenn das Ereignis regelmäßig auftritt und als Teil der normalen Programmausführung betrachtet werden kann, suchen Sie nach Fehlerbedingungen im Code. Durch Suchen und Beheben allgemeiner Fehlerbedingungen wird weniger Code ausgeführt, da Ausnahmen vermieden werden.

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Entwerfen von Klassen mit dem Ziel, Ausnahmen zu vermeiden

Eine Klasse kann Methoden oder Eigenschaften bereitstellen, mit deren Hilfe ein Aufruf vermieden werden kann, der eine Ausnahme auslösen würde. Beispielsweise stellt eine <xref:System.IO.FileStream>-Klasse Methoden bereit, mithilfe derer bestimmt werden kann, ob das Ende der Datei erreicht wurde. Dadurch kann die Ausnahme vermieden werden, die durch den Versuch ausgelöst wird, nach Erreichen des Dateiendes weiterzulesen. Das folgende Beispiel zeigt, wie eine Datei bis zum Ende gelesen werden kann, ohne dass eine Ausnahme ausgelöst wird.

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

Eine andere Möglichkeit zum Vermeiden von Ausnahmen besteht darin, `null` für sehr häufig auftretende Fehler zurückzugeben, anstatt eine Ausnahme auszulösen. Ein sehr häufig auftretender Fehler kann als normale Ablaufsteuerung betrachtet werden. Indem Sie in diesen Fällen `null` zurückgeben, minimieren Sie die Auswirkungen auf die Leistung einer App.

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Auslösen von Ausnahmen statt Zurückgeben eines Fehlercodes

Ausnahmen stellen sicher, dass Fehler nicht unbemerkt bleiben, weil der aufrufende Code einen Rückgabecode nicht überprüft hat.

## <a name="use-the-predefined-net-exception-types"></a>Verwenden der vordefinierten .NET-Ausnahmetypen

Führen Sie eine neue Ausnahmenklasse nur ein, wenn keine vordefinierte zutrifft. Beispiel:

- Lösen Sie eine <xref:System.InvalidOperationException>-Ausnahme aus, wenn eine festgelegte Eigenschaft oder ein Methodenaufruf aufgrund des aktuellen Status des Objekts nicht geeignet ist.

- Lösen Sie eine <xref:System.ArgumentException> oder eine der vordefinierten Klassen aus, die von <xref:System.ArgumentException> abgeleitet werden, wenn ungültige Parameter übergeben werden.

## <a name="end-exception-class-names-with-the-word-exception"></a>Enden von Ausnahmeklassen auf das Wort `Exception`

Wenn eine benutzerdefinierte Ausnahme erforderlich ist, benennen Sie diese entsprechend, und leiten Sie sie von der <xref:System.Exception>-Klasse ab. Beispiel:

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a>Einschließen von drei Konstruktoren in benutzerdefinierte Ausnahmeklassen

Verwenden Sie beim Erstellen eigener Ausnahmeklassen mindestens die drei allgemeinen Konstruktoren: den Standardkonstruktor, einen Konstruktor, der eine Zeichenfolgenmeldung akzeptiert, und einen Konstruktor, der eine Zeichenfolgenmeldung und eine innere Ausnahme akzeptiert.

* <xref:System.Exception.%23ctor>, der Standardwerte verwendet.

* <xref:System.Exception.%23ctor%28System.String%29>, der eine Zeichenfolgenmeldung akzeptiert.

* <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, der eine Zeichenfolgenmeldung und eine interne Ausnahme akzeptiert.

Ein Beispiel finden Sie unter [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](how-to-create-user-defined-exceptions.md).

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Sicherstellen, dass Ausnahmedaten bei Remoteausführung von Code verfügbar sind

Stellen Sie beim Erstellen von benutzerdefinierten Ausnahmen sicher, dass die Metadaten für die Ausnahmen für remote ausgeführten Code verfügbar sind.

In .NET-Implementierungen, die App-Domänen unterstützen, können Ausnahmen z.B. über mehrere App-Domänen hinweg auftreten. Ein Beispiel: App-Domäne A erstellt App-Domäne B, die wiederum Code ausführt, der eine Ausnahme auslöst. Damit die App-Domäne A die Ausnahme ordnungsgemäß erfasst und behandelt, muss die Assembly gefunden werden, in der die durch die App-Domäne B ausgelöste Ausnahme enthalten ist. Wenn die App-Domäne B eine Ausnahme auslöst, die in einer Assembly in ihrer Anwendungsbasis enthalten ist, aber nicht in der Anwendungsbasis von App-Domäne A, kann die App-Domäne A die Ausnahme nicht finden. Daraufhin löst die Common Language Runtime eine <xref:System.IO.FileNotFoundException> aus. Um diese Situation zu vermeiden, haben Sie zwei Möglichkeiten, die Assembly mit den Ausnahmeinformationen bereitzustellen:

- Legen Sie die Assembly in einer gemeinsamen Anwendungsbasis ab, die sich beide App-Domänen teilen.

    \- oder –

- Wenn die Domänen keine gemeinsame Anwendungsbasis verwenden, signieren Sie die Assembly, in der die Ausnahmeinformationen enthalten sind, mit einem starken Namen und legen sie in einem globalen Assemblycache ab.

## <a name="use-grammatically-correct-error-messages"></a>Verwenden von grammatisch korrekten Fehlermeldungen

Verfassen Sie klar verständliche Meldungen, und setzen Sie Satzendpunkte. Jeder Satz in der Zeichenfolge, der einer <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft zugeordnet ist, sollte mit einem Punkt enden. Beispiel: „In der Protokolltabelle ist ein Überlauf aufgetreten.“ Dies ist ein Beispiel für eine angemessene Meldungszeichenfolge.

## <a name="include-a-localized-string-message-in-every-exception"></a>Einschließen einer lokalisierten Meldungszeichenfolge in jede Ausnahme

Die dem Benutzer angezeigte Fehlermeldung wird von der <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft der ausgelösten Ausnahme abgeleitet, nicht vom Namen der Ausnahmeklasse. In der Regel können Sie der <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft einen Wert zuweisen, indem Sie die Meldungszeichenfolge an das `message`-Argument eines [Ausnahmekonstruktors](xref:System.Exception.%23ctor%2A) übergeben.

Sie sollten für lokalisierte Anwendungen eine lokalisierte Meldungszeichenfolge für jede Ausnahme angeben, die Ihre Anwendung ausgeben könnte. Verwenden Sie Ressourcendateien, um lokalisierte Fehlermeldungen zur Verfügung zu stellen. Weitere Informationen zum Lokalisieren von Anwendungen und Abrufen von lokalisierten Zeichenfolgen finden Sie unter [Ressourcen in Desktop-Apps](../../framework/resources/index.md) und <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>Bereitstellen zusätzlicher Eigenschaften in benutzerdefinierten Ausnahmen, sofern erforderlich

Geben Sie zusätzliche Eigenschaften für eine Ausnahme nur dann neben der benutzerdefinierten Meldungszeichenfolge an, wenn es ein programmgesteuertes Szenario gibt, in dem dieser Zusatz sinnvoll ist. Beispielsweise gibt die <xref:System.IO.FileNotFoundException> die <xref:System.IO.FileNotFoundException.FileName>-Eigenschaft an.

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Platzieren von throw-Anweisungen so, dass die Stapelüberwachung nützlich ist

Die Stapelüberwachung beginnt mit der Anweisung, bei der die Ausnahme ausgelöst wurde, und endet mit der `catch`-Anweisung, mit der die Ausnahme abgefangen wird.

## <a name="use-exception-builder-methods"></a>Verwenden von Methoden zum Generieren von Ausnahmen

Es ist üblich, dass eine Klasse von unterschiedlichen Punkten in der Implementierung aus die gleiche Ausnahme auslöst. Verwenden Sie Hilfsmethoden, die eine Ausnahme erstellen und zurückgeben, um ausufernden Code zu vermeiden. Beispiel:

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

In einigen Fällen ist es besser, den Konstruktor einer Ausnahme zu verwenden, um die Ausnahme zu generieren. Ein Beispiel hierfür ist eine globale Ausnahmeklasse wie etwa <xref:System.ArgumentException>.

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a>Wiederherstellen des Status, wenn Methoden aufgrund von Ausnahmen nicht abgeschlossen werden

Aufrufer sollten davon ausgehen können, dass keine Nebeneffekte auftreten, wenn eine Ausnahme von einer Methode ausgelöst wird. Ein Beispiel: Sie haben Code für Geldüberweisungen geschrieben. Ihr Code bucht Geld von einem Konto ab und zahlt es auf ein anderes Konto ein. Wenn nun beim Ausführen der Einzahlung eine Ausnahme ausgelöst wird, sollte die Abbuchung natürlich nicht in Kraft bleiben.

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

Die obige Methode löst keine Ausnahmen direkt aus, sondern muss defensiv geschrieben werden, sodass beim Fehlschlagen der Einzahlung die Abbuchung rückgängig gemacht wird.

In dieser Situation besteht eine Möglichkeit darin, alle Ausnahmen abzufangen, die von der Einzahlungstransaktion ausgelöst wurden, und für die Abbuchung ein Rollback auszuführen.

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

Dieses Beispiel veranschaulicht die Verwendung von `throw`, um die ursprüngliche Ausnahme erneut auszulösen, damit Aufrufer die tatsächliche Ursache des Problems erkennen können, ohne die <xref:System.Exception.InnerException>-Eigenschaft untersuchen zu müssen. Eine Alternative ist es, eine neue Ausnahme auszulösen und die ursprüngliche Ausnahme als innere Ausnahme einzuschließen:

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
