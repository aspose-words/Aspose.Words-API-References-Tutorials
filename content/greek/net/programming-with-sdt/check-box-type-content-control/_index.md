---
title: Πλαίσιο ελέγχου Τύπος Έλεγχος περιεχομένου
linktitle: Πλαίσιο ελέγχου Τύπος Έλεγχος περιεχομένου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να δημιουργήσετε ένα πλαίσιο ελέγχου Τύπος στοιχείου ελέγχου περιεχομένου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/check-box-type-content-control/
---

Αυτό το σεμινάριο εξηγεί πώς μπορείτε να δημιουργήσετε ένα στοιχείο ελέγχου περιεχομένου πλαισίου ελέγχου τύπου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Τα στοιχεία ελέγχου περιεχομένου πλαισίου ελέγχου επιτρέπουν στους χρήστες να επιλέξουν ή να διαγράψουν ένα πλαίσιο ελέγχου εντός του εγγράφου.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"`με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα Document and DocumentBuilder
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`DocumentBuilder` για τη δημιουργία του περιεχομένου του εγγράφου.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Προσθέστε ένα πλαίσιο ελέγχου Τύπος ελέγχου περιεχομένου
 Δημιουργώ ένα`StructuredDocumentTag` με`SdtType.Checkbox` για την αναπαράσταση του πλαισίου ελέγχου ελέγχου περιεχομένου. Προσδιορίζω`MarkupLevel.Inline` για να το τοποθετήσετε μέσα στο κείμενο.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save`μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Παράδειγμα πηγαίου κώδικα για Έλεγχος περιεχομένου τύπου πλαισίου ελέγχου με χρήση του Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Αυτό είναι! Δημιουργήσατε επιτυχώς ένα πλαίσιο ελέγχου Τύπος στοιχείου ελέγχου περιεχομένου στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.