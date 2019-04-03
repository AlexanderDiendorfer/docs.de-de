---
title: 'Vorgehensweise: Erstellen von XML-Dokumentation in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 2f32847c1b3a0fdf1892d6b423bb33783b6bdfe3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814587"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Vorgehensweise: Erstellen von XML-Dokumentation in Visual Basic
Dieses Beispiel zeigt, wie Sie XML-Dokumentationskommentare zu Ihrem Code hinzufügen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Um XML-Dokumentation für einen Typ oder Member zu erstellen.  
  
1.  In der **Code-Editor**, positionieren Sie den Cursor in die Zeile über den Typ oder Member, für die Erstellung der Dokumentation werden sollen.  
  
2.  Typ `'''` (drei einfache Anführungszeichen).  
  
     Ein XML-Gerüst für den Typ oder Member hinzugefügt wird, die **Code-Editor**.  
  
3.  Hinzufügen von beschreibenden Informationen zwischen den entsprechenden Tags.  
  
    > [!NOTE]
    >  Wenn Sie zusätzliche Zeilen innerhalb des Blocks des XML-Dokumentation hinzufügen, muss jede Zeile mit beginnen `'''`.  
  
4.  Fügen Sie zusätzlichen Code, der den Typ oder Member mit dem neuen XML-Dokumentationskommentaren verwendet.  
  
     IntelliSense zeigt den Text aus der \<summary >-Tag für den Typ oder Member.  
  
5.  Kompilieren Sie den Code zum Generieren einer XML-Datei, die die Dokumentationskommentare enthält. Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Siehe auch

- [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
