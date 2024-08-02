---
title: Εμφάνιση αναθεωρήσεων σε μπαλόνια
linktitle: Εμφάνιση αναθεωρήσεων σε μπαλόνια
second_title: Aspose.Words Document Processing API
description: Εμφάνιση αναθεωρήσεων σε μπαλόνια με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-revisions/show-revisions-in-balloons/
---

Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας δείξουμε πώς να εμφανίζετε αναθεωρήσεις σε μπαλόνια σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας παρέχουμε τον πλήρη πηγαίο κώδικα και θα σας δείξουμε πώς να μορφοποιήσετε την έξοδο σήμανσης.

## Βήμα 1: Φόρτωση του εγγράφου

Το πρώτο βήμα είναι να ανεβάσετε το έγγραφο που περιέχει τις αναθεωρήσεις.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Βήμα 2: Διαμόρφωση επιλογών εμφάνισης κριτικής

Θα διαμορφώσουμε τις επιλογές εμφάνισης για να κάνουμε τις αναθεωρήσεις ορατές στα μπαλόνια.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Βήμα 3: Αποθηκεύστε το έγγραφο σε μορφή PDF

Τέλος, θα αποθηκεύσουμε το έγγραφο ως PDF με τις αναθεωρήσεις που εμφανίζονται σε μπαλόνια.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Μορφές εξόδου Markdown

Η έξοδος μπορεί να μορφοποιηθεί σε μαρκάρισμα για να βελτιωθεί η αναγνωσιμότητα. Για παράδειγμα :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Παράδειγμα πηγαίου κώδικα για Εμφάνιση αναθεωρήσεων σε μπαλόνια με χρήση του Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για την εμφάνιση αναθεωρήσεων σε μπαλόνια σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Αποδίδει εισαγωγή αναθεωρήσεων ενσωματωμένη, διαγραφή και μορφοποίηση αναθεωρήσεων σε μπαλόνια.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Αποδίδει γραμμές αναθεώρησης στη δεξιά πλευρά μιας σελίδας.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να εμφανίζουμε αναθεωρήσεις σε μπαλόνια σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Χρησιμοποιώντας τις κατάλληλες επιλογές εμφάνισης, μπορέσαμε να κάνουμε τις αναθεωρήσεις ορατές σε φυσαλίδες με γραμμές αναθεώρησης στη δεξιά πλευρά. Το Aspose.Words για .NET προσφέρει πολλές ισχυρές δυνατότητες για τον χειρισμό εγγράφων του Word, συμπεριλαμβανομένης της διαχείρισης αναθεωρήσεων. Τώρα μπορείτε να χρησιμοποιήσετε αυτή τη γνώση για να εμφανίσετε αναθεωρήσεις σε μπαλόνια στα δικά σας έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.


### Συχνές ερωτήσεις

#### Ε: Πώς να ανεβάσετε ένα έγγραφο στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Document` κλάση Aspose.Words για .NET για τη φόρτωση ενός εγγράφου από ένα αρχείο. Μπορείτε να καθορίσετε την πλήρη διαδρομή του εγγράφου.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Ε: Πώς να εμφανίσετε αναθεωρήσεις σε μπαλόνια με το Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`ShowInBalloons` ιδιοκτησία του`RevisionOptions` αντικείμενο να ρυθμίσετε την εμφάνιση των αναθεωρήσεων σε μπαλόνια. Μπορείτε να ρυθμίσετε αυτήν την ιδιότητα`ShowInBalloons.FormatAndDelete` για εμφάνιση αναθεωρήσεων σε μπαλόνια με αναθεωρήσεις διαγραφής και μορφοποίησης.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Ε: Πώς να αποθηκεύσετε ένα έγγραφο σε μορφή PDF με το Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Save` μέθοδος του`Document` αντικείμενο αποθήκευσης του εγγράφου σε μορφή PDF. Πρέπει να καθορίσετε την πλήρη διαδρομή προορισμού με την επέκταση ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```