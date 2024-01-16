---
title: Κατάργηση σχολίων σε αρχείο Pdf
linktitle: Κατάργηση σχολίων σε αρχείο Pdf
second_title: Aspose.Words Document Processing API
description: Καταργήστε τα σχόλια σε ένα αρχείο PDF με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-revisions/remove-comments-in-pdf/
---

Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας πούμε πώς να αφαιρέσετε σχόλια σε ένα αρχείο PDF χρησιμοποιώντας το Aspose.Words για .NET. Θα σας παρέχουμε τον πλήρη πηγαίο κώδικα και θα σας δείξουμε πώς να μορφοποιήσετε την έξοδο σήμανσης.

## Βήμα 1: Φόρτωση του εγγράφου

Το πρώτο βήμα είναι να φορτώσετε το έγγραφο που περιέχει τα σχόλια.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Βήμα 2: Απόκρυψη σχολίων σε PDF

Θα διαμορφώσουμε την επιλογή διάταξης για απόκρυψη σχολίων κατά τη δημιουργία του PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Βήμα 3: Αποθηκεύστε το έγγραφο ως PDF

Τέλος, θα αποθηκεύσουμε το έγγραφο σε μορφή PDF διαγράφοντας τα σχόλια.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Μορφές εξόδου Markdown

Η έξοδος μπορεί να μορφοποιηθεί σε μαρκάρισμα για να βελτιωθεί η αναγνωσιμότητα. Για παράδειγμα :

```markdown
- Comments are hidden in the generated PDF.
```

### Παράδειγμα πηγαίου κώδικα για Κατάργηση σχολίων σε Pdf χρησιμοποιώντας Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για την κατάργηση σχολίων σε ένα αρχείο PDF χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Απόκρυψη σχολίων στο PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να αφαιρούμε σχόλια από ένα αρχείο PDF χρησιμοποιώντας το Aspose.Words για .NET. Χρησιμοποιώντας τις κατάλληλες επιλογές διάταξης, μπορέσαμε να αποκρύψουμε τα σχόλια κατά τη δημιουργία του PDF. Το Aspose.Words για .NET προσφέρει μεγάλη ευελιξία για το χειρισμό αρχείων του Word και τη μετατροπή τους σε διαφορετικές μορφές, συμπεριλαμβανομένου του PDF. Τώρα μπορείτε να εφαρμόσετε αυτήν τη γνώση για να αφαιρέσετε σχόλια στα δικά σας αρχεία PDF χρησιμοποιώντας το Aspose.Words για .NET.

### Συχνές ερωτήσεις για την αφαίρεση σχολίων σε αρχείο pdf

#### Ε: Πώς να ανεβάσετε ένα έγγραφο στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Document` κλάση Aspose.Words για .NET για τη φόρτωση ενός εγγράφου από ένα αρχείο. Μπορείτε να καθορίσετε την πλήρη διαδρομή του εγγράφου.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Ε: Πώς να αποκρύψετε σχόλια σε PDF που δημιουργήθηκαν με το Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`CommentDisplayMode` ιδιοκτησία του`LayoutOptions` αντικείμενο να ρυθμίσετε τον τρόπο εμφάνισης των σχολίων κατά τη δημιουργία του PDF. Για απόκρυψη σχολίων, ορίστε αυτήν την ιδιότητα σε`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Ε: Πώς να αποθηκεύσετε ένα έγγραφο ως PDF με το Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Save` μέθοδος του`Document` αντικείμενο αποθήκευσης του εγγράφου σε μορφή PDF. Καθορίστε την πλήρη διαδρομή του αρχείου PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```