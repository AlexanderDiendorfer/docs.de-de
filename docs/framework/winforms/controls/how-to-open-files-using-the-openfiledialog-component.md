---
title: 'Vorgehensweise: Öffnen von Dateien mit der OpenFileDialog-Komponente'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 5781543a61d77ef8f0658e95759c57fdb77cfc4f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723087"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Vorgehensweise: Mit der OpenFileDialog geöffneten Dateien 

Die <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> Komponente Öffnet das Dialogfeld "Windows", für das Durchsuchen und Auswählen von Dateien. Öffnen und die ausgewählte Dateien lesen, können Sie die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> -Methode, oder erstellen Sie eine Instanz von der <xref:System.IO.StreamReader?displayProperty=nameWithType> Klasse. In den folgenden Beispielen werden beide Ansätze gezeigt. 

In .NET Framework zum Abrufen oder Festlegen der <xref:System.Windows.Forms.FileDialog.FileName%2A> Eigenschaft benötigt eine Berechtigungsebene gewährt, durch die <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> Klasse. Ausführen der Beispiele ein <xref:System.Security.Permissions.FileIOPermission> Berechtigung überprüfen, und kann aufgrund fehlender Berechtigungen eine Ausnahme auslösen, wenn in einer teilweise vertrauenswürdigen Kontext ausgeführt werden. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).

Können Sie erstellen und Ausführen dieser Beispiele als .NET Framework-apps aus dem C# oder Visual Basic über die Befehlszeile. Weitere Informationen finden Sie unter [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

Ab .NET Core 3.0, Sie können auch erstellen und Ausführen der Beispiele als Windows .NET Core-apps aus einem Ordner, die eine .NET Core Windows Forms  *\<Ordnername > .csproj* Projektdatei. 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Beispiel: Lesen einer Datei als Stream mit StreamReader  
  
Im folgenden Beispiel wird die Windows-Formulare <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler zum Öffnen der <xref:System.Windows.Forms.OpenFileDialog> mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode. Nachdem der Benutzer eine Datei wählt und wählt **OK**, eine Instanz von der <xref:System.IO.StreamReader> Klasse liest die Datei und ihr Inhalt im Textfeld des Formulars angezeigt. Weitere Informationen zum Lesen aus Dateistreams finden Sie unter <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> und <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Beispiel: Öffnen Sie eine Datei aus einer gefilterten mit OpenFile-Auswahl 

Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler zum Öffnen der <xref:System.Windows.Forms.OpenFileDialog> mit einem Filter, die nur-Text-Dateien anzeigt. Nachdem der Benutzer eine Textdatei wählt, und wählt **OK**, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methode wird verwendet, um die Datei im Editor zu öffnen.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog-Komponente](openfiledialog-component-windows-forms.md)
