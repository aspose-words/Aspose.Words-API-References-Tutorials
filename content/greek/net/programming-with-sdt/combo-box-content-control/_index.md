---
title: Έλεγχος περιεχομένου Combo Box
linktitle: Έλεγχος περιεχομένου Combo Box
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε ένα στοιχείο ελέγχου περιεχομένου Combo Box σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/combo-box-content-control/
---

Αυτό το σεμινάριο εξηγεί πώς να δημιουργήσετε ένα Combo Box Content Control σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Τα στοιχεία ελέγχου περιεχομένου σύνθετου πλαισίου επιτρέπουν στους χρήστες να επιλέξουν ένα στοιχείο από μια αναπτυσσόμενη λίστα.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα έγγραφο και ένα StructuredDocumentTag
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`StructuredDocumentTag` για να αναπαραστήσετε το στοιχείο ελέγχου περιεχομένου σύνθετου πλαισίου. Προσδιορίζω`SdtType.ComboBox` ως ο τύπος και`MarkupLevel.Block` ως επίπεδο σήμανσης για τη δημιουργία ενός σύνθετου πλαισίου σε επίπεδο μπλοκ.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Βήμα 3: Προσθέστε στοιχεία στο Combo Box
 Προσθέστε στοιχεία στο σύνθετο πλαίσιο χρησιμοποιώντας το`ListItems` ιδιοκτησία του`StructuredDocumentTag` . Κάθε στοιχείο αντιπροσωπεύεται από ένα`SdtListItem` αντικείμενο, το οποίο παίρνει ένα κείμενο εμφάνισης και μια τιμή. Σε αυτό το παράδειγμα, προσθέτουμε τρία στοιχεία στο σύνθετο πλαίσιο.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Βήμα 4: Προσθέστε το StructuredDocumentTag στο έγγραφο
 Προσθέστε το στοιχείο ελέγχου περιεχομένου σύνθετου πλαισίου στο σώμα του εγγράφου χρησιμοποιώντας το`AppendChild` μέθοδο του σώματος του πρώτου τμήματος του εγγράφου.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Βήμα 5: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Παράδειγμα πηγαίου κώδικα για Combo Box Content Control χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Αυτό είναι! Δημιουργήσατε επιτυχώς ένα στοιχείο ελέγχου περιεχομένου Combo Box στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.