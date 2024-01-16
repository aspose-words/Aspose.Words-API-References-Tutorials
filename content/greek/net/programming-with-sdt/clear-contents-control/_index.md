---
title: Εκκαθάριση ελέγχου περιεχομένου
linktitle: Εκκαθάριση ελέγχου περιεχομένου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να διαγράψετε τα περιεχόμενα ενός στοιχείου ελέγχου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/clear-contents-control/
---

Αυτό το σεμινάριο δείχνει πώς να διαγράψετε τα περιεχόμενα ενός SDT σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Η εκκαθάριση των περιεχομένων ενός SDT καταργεί οποιοδήποτε κείμενο ή θυγατρικούς κόμβους εντός του στοιχείου ελέγχου περιεχομένου.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφό σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο και λάβετε το StructuredDocumentTag
 Φορτώστε το έγγραφο του Word χρησιμοποιώντας το`Document` κατασκευαστή, περνώντας τη διαδρομή προς το έγγραφο ως παράμετρο. Στη συνέχεια, ανακτήστε το επιθυμητό`StructuredDocumentTag` από το έγγραφο. Σε αυτό το παράδειγμα, υποθέτουμε ότι ο SDT είναι ο πρώτος θυγατρικός κόμβος στο έγγραφο.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Βήμα 3: Διαγράψτε τα περιεχόμενα της ετικέτας StructuredDocument
 Διαγράψτε τα περιεχόμενα του SDT χρησιμοποιώντας το`Clear` μέθοδος. Αυτό καταργεί οποιοδήποτε κείμενο ή θυγατρικούς κόμβους εντός του στοιχείου ελέγχου περιεχομένου.

```csharp
sdt.Clear();
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το τροποποιημένο έγγραφο χρησιμοποιώντας το`Save`μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Παράδειγμα πηγαίου κώδικα για το Clear Contents Control με χρήση του Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Αυτό είναι! Έχετε διαγράψει επιτυχώς τα περιεχόμενα ενός StructuredDocumentTag στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.