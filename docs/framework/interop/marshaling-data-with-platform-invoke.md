---
title: Marshallen von Daten mit Plattformaufruf
ms.date: 03/20/2019
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 396dc1dec60a6a984f9ddd0b8a8753b7293a5ab9
ms.sourcegitcommit: 77854e8704b9689b73103d691db34d71c2bf1dad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "58307862"
---
# <a name="marshaling-data-with-platform-invoke"></a>Marshallen von Daten mit Plattformaufruf

Zum Aufrufen von Funktionen, die aus einer unverwalteten Bibliothek exportiert wurden, erfordert eine .NET Framework-Anwendung einen Funktionsprototypen im verwalteten Code, der die unverwaltete Funktion darstellt. Gehen Sie zum Erstellen eines Prototypen, der den Aufruf der Plattform für das korrekte Marshalling von Daten ermöglicht, gehen Sie folgendermaßen vor:

- Wenden Sie das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut auf die statische Funktion oder Methode im verwalteten Code an.

- Ersetzen Sie verwaltete Datentypen durch unverwaltete Datentypen.

Sie können die mit einer unverwalteten Funktion bereitgestellten Dokumentation verwendet, um einen äquivalenten verwalteten Prototypen zu erstellen, indem Sie das Attribut mit seinen optionalen Feldern anwenden und verwaltete Datentypen durch unverwaltete Datentypen ersetzen. Anweisungen zum Anwenden von **DllImportAttribute** finden Sie unter [Consuming Unmanaged DLL Functions (Verwenden nicht verwalteter DLL-Funktionen)](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).

Dieser Abschnitt enthält Beispiele, die zeigen, wie Prototypen für verwaltete Funktionen erstellt werden, an die Argumente übergeben und von denen Werte von Funktionen zurückgegeben werden, die aus unverwalteten Bibliotheken exportiert wurden. Die Beispiele zeigen auch, wann das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut und die <xref:System.Runtime.InteropServices.Marshal>-Klasse zum expliziten Marshallen von Daten verwendet werden.

## <a name="platform-invoke-data-types"></a>Datentypen für den Plattformaufruf

Die folgende Tabelle listet die Datentypen auf, die in der WIN 32-API (aufgeführt in Wtypes.h) verwendet werden, und die Funktionen im C-Stil auf. Viele unverwaltete Bibliotheken enthalten Funktionen, die diese Datentypen als Parameter und Rückgabewerte übergeben. Die dritte Spalte enthält den entsprechenden in .NET Framework integrierten Werttype oder die Klasse, die Sie in verwaltetem Code verwenden. In einigen Fällen können Sie einen Typ der gleichen Größe durch den in der Tabelle aufgeführten Typ ersetzen.

|Unverwalteter Typ in Wtypes.h|Unverwalteter Typ in C-Sprache|Name des verwalteten Typs|Beschreibung|
|--------------------------------|-------------------------------|------------------------|-----------------|
|**VOID**|**void**|<xref:System.Void?displayProperty=nameWithType>|Auf eine Funktion angewendet, die keinen Wert zurückgibt|
|**HANDLE**|**void \***|<xref:System.IntPtr?displayProperty=nameWithType> oder <xref:System.UIntPtr?displayProperty=nameWithType>|32 Bit unter 32-Bit-Windows-Betriebssystemen, 64 Bit unter 64-Bit-Windows-Betriebssystemen.|
|**BYTE**|**unsigned char**|<xref:System.Byte?displayProperty=nameWithType>|8 Bit|
|**SHORT**|**short**|<xref:System.Int16?displayProperty=nameWithType>|16 Bit|
|**WORD**|**unsigned short**|<xref:System.UInt16?displayProperty=nameWithType>|16 Bit|
|**INT**|**int**|<xref:System.Int32?displayProperty=nameWithType>|32 Bit|
|**UINT**|**unsigned int**|<xref:System.UInt32?displayProperty=nameWithType>|32 Bit|
|**LONG**|**long**|<xref:System.Int32?displayProperty=nameWithType>|32 Bit|
|**BOOL**|**long**|<xref:System.Boolean?displayProperty=nameWithType> oder <xref:System.Int32?displayProperty=nameWithType>|32 Bit|
|**DWORD**|**unsigned long**|<xref:System.UInt32?displayProperty=nameWithType>|32 Bit|
|**ULONG**|**unsigned long**|<xref:System.UInt32?displayProperty=nameWithType>|32 Bit|
|**CHAR**|**char**|<xref:System.Char?displayProperty=nameWithType>|Mit ANSI ergänzen.|
|**WCHAR**|**wchar_t**|<xref:System.Char?displayProperty=nameWithType>|Mit Unicode ergänzen.|
|**LPSTR**|**char &ast;**|<xref:System.String?displayProperty=nameWithType> oder <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Mit ANSI ergänzen.|
|**LPCSTR**|**const char &ast;**|<xref:System.String?displayProperty=nameWithType> oder <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Mit ANSI ergänzen.|
|**LPWSTR**|**wchar_t &ast;**|<xref:System.String?displayProperty=nameWithType> oder <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Mit Unicode ergänzen.|
|**LPCWSTR**|**const wchar_t &ast;**|<xref:System.String?displayProperty=nameWithType> oder <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Mit Unicode ergänzen.|
|**FLOAT**|**float**|<xref:System.Single?displayProperty=nameWithType>|32 Bit|
|**DOUBLE**|**double**|<xref:System.Double?displayProperty=nameWithType>|64 Bit|

Informationen zu den entsprechenden Typen in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# und C++ finden Sie unter [Einführung in die .NET Framework-Klassenbibliothek](../../../docs/standard/class-library-overview.md).

## <a name="pinvokelibdll"></a>PinvokeLib.dll

Mit dem folgenden Code werden die Bibliotheksfunktionen definiert, die von der Pinvoke.dll bereitgestellt werden. Viele Beispiele in diesem Abschnitt rufen diese Bibliothek auf.

### <a name="example"></a>Beispiel

[!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]

[!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]
