---
title: 'Vorgehensweise: Definieren Sie eine Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 61f0c99560d008cc10c94403ac936e5b97267d3a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707650"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Vorgehensweise: Definieren Sie eine Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche mithilfe des Designers
Auf jedem Windows-Formular, Sie können festlegen, eine <xref:System.Windows.Forms.Button> Steuerelement "Annehmen"-Schaltfläche, auch bekannt als die Standardschaltfläche. Wenn der Benutzer die EINGABETASTE drückt, wird die Schaltfläche "Standard" geklickt haben, unabhängig davon, welche anderen Formular auf das Steuerelement den Fokus besitzt. Die Ausnahmen von dieser sind, wenn das Steuerelement mit Fokus auf eine andere Schaltfläche ist – in diesem Fall wird die Schaltfläche mit den Fokus geklickt werden, oder ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das fängt die EINGABETASTE.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-designate-the-accept-button"></a>Festlegen von "Annehmen"-Schaltfläche  
  
1.  Wählen Sie das Formular, das auf dem sich die Schaltfläche befindet.  
  
2.  In der **Eigenschaften** legen des Formulars <xref:System.Windows.Forms.Form.AcceptButton%2A> Eigenschaft, um die <xref:System.Windows.Forms.Button> Name des Steuerelements.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt](how-to-respond-to-windows-forms-button-clicks.md)
- [Vorgehensweise: Festlegen einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche mithilfe des Designers](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button-Steuerelement](button-control-windows-forms.md)
