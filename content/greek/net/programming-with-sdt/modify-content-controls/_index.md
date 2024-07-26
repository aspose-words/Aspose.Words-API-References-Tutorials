---
title: Τροποποίηση στοιχείων ελέγχου περιεχομένου
linktitle: Τροποποίηση στοιχείων ελέγχου περιεχομένου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να τροποποιείτε κείμενο, αναπτυσσόμενες λίστες και εικόνες εντός των στοιχείων ελέγχου περιεχομένου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/modify-content-controls/
---

Αυτό το σεμινάριο εξηγεί πώς μπορείτε να τροποποιήσετε διαφορετικούς τύπους στοιχείων ελέγχου περιεχομένου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Μπορείτε να ενημερώσετε το κείμενο, την επιλεγμένη τιμή μιας αναπτυσσόμενης λίστας ή να αντικαταστήσετε μια εικόνα στα στοιχεία ελέγχου περιεχομένου.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφό σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φόρτωση του εγγράφου και επανάληψη των στοιχείων ελέγχου περιεχομένου
 Φορτώστε το έγγραφο του Word χρησιμοποιώντας το`Document` κατασκευαστή, περνώντας τη διαδρομή προς το έγγραφο ως παράμετρο. Επανάληψη σε όλες τις ετικέτες δομημένου εγγράφου στο έγγραφο χρησιμοποιώντας α`foreach` βρόχος.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Εκτελέστε ενέργειες με βάση τον τύπο ελέγχου περιεχομένου
}
```

## Βήμα 3: Τροποποίηση ελέγχου περιεχομένου απλού κειμένου
 Για ελέγχους περιεχομένου τύπου`SdtType.PlainText`, αφαιρέστε όλα τα υπάρχοντα παιδιά, δημιουργήστε μια νέα παράγραφο και προσθέστε μια εκτέλεση με το επιθυμητό κείμενο.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Βήμα 4: Τροποποίηση ελέγχου περιεχομένου της αναπτυσσόμενης λίστας
 Για ελέγχους περιεχομένου τύπου`SdtType.DropDownList` , ενημερώστε την επιλεγμένη τιμή ορίζοντας την σε μια συγκεκριμένη`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Βήμα 5: Τροποποίηση ελέγχου περιεχομένου εικόνας
 Για ελέγχους περιεχομένου τύπου`SdtType.Picture`, ανακτήστε το σχήμα μέσα στο στοιχείο ελέγχου περιεχομένου και αντικαταστήστε την εικόνα του με μια νέα.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Βήμα 6: Αποθηκεύστε το τροποποιημένο έγγραφο
 Αποθηκεύστε το τροποποιημένο έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Παράδειγμα πηγαίου κώδικα για Τροποποίηση στοιχείων ελέγχου περιεχομένου χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Αυτό είναι! Έχετε τροποποιήσει με επιτυχία διαφορετικούς τύπους στοιχείων ελέγχου περιεχομένου στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.