---
title: 'Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: f2831333008844c959c3625698fce6c485450683
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967554"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic
In diesem Beispiel wird veranschaulicht, wie die <xref:System.String.Chars%2A> Eigenschaft, um das Zeichen an der angegebenen Position in einer Zeichenfolge zuzugreifen.  
  
## <a name="example"></a>Beispiel  
 Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der diese Zeichen in der Zeichenfolge. Sie können als ein Array von Zeichen einer Zeichenfolge vorstellen (`Char` Instanzen); Sie können ein bestimmtes Zeichen abrufen, indem Sie auf den Index des Zeichens durch Verweisen der <xref:System.String.Chars%2A> Eigenschaft.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 Die `index` Parameter, der die <xref:System.String.Chars%2A> Eigenschaft ist nullbasiert.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die <xref:System.String.Chars%2A> Eigenschaft gibt das Zeichen an der angegebenen Position zurück. Allerdings können einige Unicode-Zeichen durch mehr als ein Zeichen dargestellt werden. Weitere Informationen zum Arbeiten mit Unicode-Zeichen finden Sie unter [Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 Die <xref:System.String.Chars%2A> Eigenschaft löst eine <xref:System.IndexOutOfRangeException> Ausnahme wenn die `index` -Parameter ist größer als oder gleich der Länge der Zeichenfolge ist, oder wenn es kleiner als 0 (null)  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.String.Chars%2A>
- [Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
