---
title: 'Vorgehensweise: Reagieren Sie auf Windows Forms das Klicken auf Kontrollkästchen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: fff08bebf4e0eeea7dff8146ed8805e9d71247da
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724501"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Vorgehensweise: Reagieren Sie auf Windows Forms das Klicken auf Kontrollkästchen
Jedes Mal, wenn ein Benutzer klickt ein Windows Forms <xref:System.Windows.Forms.CheckBox> -Steuerelement, das <xref:System.Windows.Forms.Control.Click> Ereignis auftritt. Sie können Ihre Anwendung zum Ausführen einer Aktion, die je nach Zustand des Kontrollkästchens programmieren.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Um auf das Klicken auf Kontrollkästchen zu reagieren  
  
1.  In der <xref:System.Windows.Forms.Control.Click> -Ereignishandler der <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft, um den Zustand des Steuerelements zu bestimmen, und führen Sie alle erforderlichen Aktionen.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  Wenn der Benutzer versucht, doppelklicken Sie auf die <xref:System.Windows.Forms.CheckBox> -Steuerelement, jedem Klick wird separat verarbeitet werden, d. h. die <xref:System.Windows.Forms.CheckBox> Steuerelement unterstützt nicht das Doppelklickereignis.  
  
    > [!NOTE]
    >  Wenn die <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> -Eigenschaft ist `true` (Standardeinstellung), die <xref:System.Windows.Forms.CheckBox> automatisch aktiviert oder deaktiviert werden, wenn darauf geklickt wird. Andernfalls müssen Sie manuell festlegen der <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft bei der <xref:System.Windows.Forms.Control.Click> Ereignis tritt auf.  
  
     Sie können auch die <xref:System.Windows.Forms.CheckBox> Steuerelement, um zu bestimmen, welche Aktion.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Um zu bestimmen, Aktion, wenn das Kontrollkästchen geklickt wird  
  
1.  Eine Case-Anweisung den Wert der Abfragen verwenden die <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft, um eine Aktion zu bestimmen. Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft kann drei mögliche Werte, die das Feld, das zu überprüfende darstellen, zurück Kontrollkästchen deaktiviert wird, oder ein Drittanbieterserver unbestimmten Zustand, in dem das Feld angezeigt wird, mit einem abgeblendet Darstellung an, dass die Option ist nicht verfügbar.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> -Eigenschaft gibt `true` für beide <xref:System.Windows.Forms.CheckState.Checked> und <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.CheckBox>
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [Vorgehensweise: Festlegen von Optionen mit CheckBox-Steuerelementen für Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [CheckBox-Steuerelement](checkbox-control-windows-forms.md)
