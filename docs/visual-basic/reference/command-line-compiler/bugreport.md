---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: e7b4ebc58b6fe9850b92ef945cb0d715e4369efe
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820910"
---
# <a name="-bugreport"></a>-bugreport
Erstellt eine Datei, die Sie verwenden können, wenn Sie einen Fehlerbericht einzureichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`file`|Erforderlich. Der Name der Datei, die den Problembericht enthalten soll. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn der Name ein Leerzeichen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Informationen wird hinzugefügt, um `file`:  
  
-   Eine Kopie aller Quellcodedateien in der Kompilierung.  
  
-   Eine Liste der in der Kompilierung verwendeten Compileroptionen.  
  
-   Versionsinformationen zu Compiler, common Language Runtime und Betriebssystem.  
  
-   Compilerausgabe, falls vorhanden.  
  
-   Eine Beschreibung des Problems, für die Sie dazu aufgefordert werden.  
  
-   Eine Beschreibung Ihres das Problem Vorschlags muss behoben werden, für die Sie dazu aufgefordert werden.  
  
 Da eine Kopie aller Quellcodedateien in enthalten ist `file`, möglicherweise möchten Sie den (vermuteten) Codefehler im kürzestmöglichen Programm zu reproduzieren.  
  
> [!IMPORTANT]
>  Die `-bugreport` Option erzeugt eine Datei, die möglicherweise vertrauliche Informationen enthält. Dies schließt die aktuelle Uhrzeit, die Version des Compilers, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Version, Betriebssystemversion, Benutzername, die Befehlszeilenargumente, klicken Sie mit der der Compiler ausgeführt wurde, werden alle Quellcode, und die binäre Form eines auf die Assembly verwiesen wird. Diese Option kann zugegriffen werden, durch die Angabe von Befehlszeilenoptionen in der Datei "Web.config" für eine serverseitige Kompilierung einer [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Anwendung. Um dies zu vermeiden, ändern Sie die Datei "Machine.config", um Benutzer an der Kompilierung auf dem Server verweigern.  
  
 Wenn diese Option verwendet wird, mit `-errorreport:prompt`, `-errorreport:queue`, oder `-errorreport:send`, und Ihre Anwendung findet einen interner Compilerfehler, die Informationen in `file` an die Microsoft Corporation gesendet. Diese Informationen helfen Microsoft-Techniker, die die Ursache des Fehlers zu identifizieren und die nächste Version von Visual Basic zu verbessern. Standardmäßig ist keine Informationen an Microsoft gesendet. Allerdings beim Kompilieren einer Anwendungs mithilfe von `-errorreport:queue`, die standardmäßig aktiviert ist, sammelt die Anwendung ihre Fehlerberichte. Anschließend bei der Administrator des Computers, zeigt das Berichterstattungssystem Fehler ein Popup-Fenster, die es den Administrator ermöglicht, die an Microsoft, die Fehlerberichte weitergeleitet, die seit der Anmeldung aufgetreten ist.  
  
> [!NOTE]
>  Die `/bugreport` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird kompiliert `T2.vb` und setzt alle für die Fehlerberichterstattung Informationen in der Datei `Problem.txt`.  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [TrustLevel-Element für SecurityPolicy ((ASP.NET Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
