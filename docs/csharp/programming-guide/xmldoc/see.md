---
title: <see> – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 90fd73346d255d195fa7384ebc2f60ebc4f32fba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480675"
---
# <a name="see-c-programming-guide"></a>\<see> (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a>Parameter  
 cref = " `member`"  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe. Setzen Sie *member* in doppelte Anführungszeichen (" ").  
  
## <a name="remarks"></a>Anmerkungen  
 Mit dem \<see>-Tag kann ein Link im Text angegeben werden. Verwenden Sie [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll. Verwenden Sie das [cref-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.  
  
 Kompilieren Sie mit [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
 Im folgenden Beispiel wird ein \<see>-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.  
  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
