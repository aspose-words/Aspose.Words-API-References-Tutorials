---
title: Τρέχουσα κατάσταση του πλαισίου ελέγχου
linktitle: Τρέχουσα κατάσταση του πλαισίου ελέγχου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ανακτάτε και να ορίζετε την τρέχουσα κατάσταση ενός στοιχείου ελέγχου περιεχομένου πλαισίου ελέγχου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/current-state-of-check-box/
---

Αυτό το σεμινάριο εξηγεί πώς να ανακτήσετε και να ορίσετε την τρέχουσα κατάσταση ενός στοιχείου ελέγχου περιεχομένου πλαισίου ελέγχου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Μπορείτε να επιλέξετε ή να αποεπιλέξετε το πλαίσιο ελέγχου με βάση την τρέχουσα κατάστασή του.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφό σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο και ανακτήστε το στοιχείο ελέγχου περιεχομένου του πλαισίου ελέγχου
 Φορτώστε το έγγραφο του Word χρησιμοποιώντας το`Document` κατασκευαστή, περνώντας τη διαδρομή προς το έγγραφο ως παράμετρο. Στη συνέχεια, ανακτήστε το επιθυμητό στοιχείο ελέγχου περιεχομένου πλαισίου ελέγχου από το έγγραφο. Σε αυτό το παράδειγμα, υποθέτουμε ότι το πλαίσιο ελέγχου είναι η πρώτη ετικέτα δομημένου εγγράφου στο έγγραφο.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Βήμα 3: Επιλέξτε ή καταργήστε την επιλογή του πλαισίου ελέγχου με βάση την τρέχουσα κατάστασή του
 Ελέγξτε εάν η ετικέτα δομημένου εγγράφου που ανακτήθηκε είναι του τύπου`SdtType.Checkbox` . Εάν είναι, ρυθμίστε το`Checked` ιδιότητα του ελέγχου περιεχομένου σε`true` για να ελέγξετε το πλαίσιο. Διαφορετικά, μπορείτε να το αφήσετε ανεξέλεγκτο.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το τροποποιημένο έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Παράδειγμα πηγαίου κώδικα για το πλαίσιο ελέγχου Τρέχουσα κατάσταση χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Λάβετε τον πρώτο έλεγχο περιεχομένου από το έγγραφο.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Αυτό είναι! Έχετε ανακτήσει και ορίσει με επιτυχία την τρέχουσα κατάσταση ενός στοιχείου ελέγχου περιεχομένου πλαισίου ελέγχου στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.