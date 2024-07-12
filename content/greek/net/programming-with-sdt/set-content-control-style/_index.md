---
title: Ορισμός στυλ ελέγχου περιεχομένου
linktitle: Ορισμός στυλ ελέγχου περιεχομένου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ορίζετε το στυλ ενός στοιχείου ελέγχου περιεχομένου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, εφαρμόζοντας συνεπή μορφοποίηση.
type: docs
weight: 10
url: /el/net/programming-with-sdt/set-content-control-style/
---

Αυτό το σεμινάριο εξηγεί πώς να ορίσετε το στυλ ενός στοιχείου ελέγχου περιεχομένου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Μπορείτε να εφαρμόσετε προκαθορισμένα ή προσαρμοσμένα στυλ σε στοιχεία ελέγχου περιεχομένου για συνεπή μορφοποίηση.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφό σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο και ανακτήστε το στοιχείο ελέγχου περιεχομένου
 Φορτώστε το έγγραφο του Word χρησιμοποιώντας το`Document` κατασκευαστή, περνώντας τη διαδρομή προς το έγγραφο ως παράμετρο. Ανακτήστε το επιθυμητό στοιχείο ελέγχου περιεχομένου από το έγγραφο. Σε αυτό το παράδειγμα, υποθέτουμε ότι το στοιχείο ελέγχου περιεχομένου είναι η πρώτη ετικέτα δομημένου εγγράφου στο έγγραφο.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Βήμα 3: Ανακτήστε το στυλ και εφαρμόστε το στον έλεγχο περιεχομένου
 Ανακτήστε το επιθυμητό στυλ από τη συλλογή στυλ του εγγράφου. Σε αυτό το παράδειγμα, ανακτούμε το στυλ "Παράθεση" χρησιμοποιώντας`StyleIdentifier.Quote` . Στη συνέχεια, αντιστοιχίστε το ανακτηθέν στυλ στο`Style` ιδιότητα της ετικέτας δομημένου εγγράφου.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το τροποποιημένο έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save`μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Παράδειγμα πηγαίου κώδικα για Ορισμός στυλ ελέγχου περιεχομένου χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Αυτό είναι! Έχετε ορίσει με επιτυχία το στυλ ενός στοιχείου ελέγχου περιεχομένου στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.