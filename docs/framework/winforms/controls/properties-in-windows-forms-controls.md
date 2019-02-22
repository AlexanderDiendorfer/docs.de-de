---
title: Eigenschaften von Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: b1f7e0f5c1c9a01e47d0d972c56db8da922d2d0b
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664574"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="1595f-102">Eigenschaften von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1595f-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="1595f-103">Ein Windows Forms-Steuerelement erbt viele Eigenschaften die Basisklasse <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1595f-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1595f-104">Hierzu gehören Eigenschaften wie z. B. <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, und viele andere.</span><span class="sxs-lookup"><span data-stu-id="1595f-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="1595f-105">Weitere Informationen zu geerbten Eigenschaften finden Sie unter <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1595f-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="1595f-106">Sie können geerbte Eigenschaften in Ihrem Steuerelement außer Kraft setzen oder neue Eigenschaften definieren.</span><span class="sxs-lookup"><span data-stu-id="1595f-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1595f-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1595f-107">In This Section</span></span>  
 [<span data-ttu-id="1595f-108">Definieren einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1595f-108">Defining a Property</span></span>](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="1595f-109">Demonstriert das Implementieren einer Eigenschaft für ein benutzerdefiniertes Steuerelement oder eine Komponente und das Integrieren der Eigenschaft in die Entwurfsumgebung.</span><span class="sxs-lookup"><span data-stu-id="1595f-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="1595f-110">Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="1595f-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="1595f-111">Demonstriert das Definieren von Standardeigenschaftswerten für ein benutzerdefiniertes Steuerelement oder eine Komponente.</span><span class="sxs-lookup"><span data-stu-id="1595f-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="1595f-112">Durch geänderte Eigenschaften ausgelöste Ereignisse</span><span class="sxs-lookup"><span data-stu-id="1595f-112">Property-Changed Events</span></span>](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 <span data-ttu-id="1595f-113">Beschreibt das Aktivieren von Benachrichtigungen über Eigenschaftsänderungen, wenn ein Eigenschaftswert geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1595f-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="1595f-114">Vorgehensweise: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="1595f-114">How to: Expose Properties of Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="1595f-115">Veranschaulicht, wie man Eigenschaften von konstituierenden Steuerelementen in einem benutzerdefinierten zusammengesetzten Steuerelement verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="1595f-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="1595f-116">Implementierung von Methoden in benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1595f-116">Method Implementation in Custom Controls</span></span>](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 <span data-ttu-id="1595f-117">Beschreibt die Implementierung von Methoden in benutzerdefinierten Steuerelementen und Komponenten.</span><span class="sxs-lookup"><span data-stu-id="1595f-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1595f-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="1595f-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="1595f-119">Dokumentiert die Basisklasse für das Implementieren von zusammengesetzten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="1595f-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="1595f-120">Dokumentiert das Attribut aus, der angibt, die <xref:System.ComponentModel.TypeConverter> , die für einen benutzerdefinierten Eigenschaftentyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="1595f-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="1595f-121">Dokumentiert das Attribut aus, der angibt, die <xref:System.Drawing.Design.UITypeEditor> für eine benutzerdefinierte Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1595f-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1595f-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1595f-122">Related Sections</span></span>  
 [<span data-ttu-id="1595f-123">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1595f-123">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="1595f-124">Beschreibt die Attribute, die Sie auf Eigenschaften oder andere Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können.</span><span class="sxs-lookup"><span data-stu-id="1595f-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="1595f-125">[Entwurfszeitattribute für Komponenten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1595f-125">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="1595f-126">Listet die Metadatenattribute für Komponenten und Steuerelemente auf, damit sie in visuellen Designern zur Entwurfszeit korrekt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1595f-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="1595f-127">[Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1595f-127">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="1595f-128">Beschreibt die Implementierung von Klassen wie Editoren und Designern, die Entwurfszeitunterstützung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1595f-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
