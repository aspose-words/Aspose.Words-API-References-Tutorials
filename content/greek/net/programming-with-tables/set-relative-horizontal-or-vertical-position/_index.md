---
title: Ορισμός σχετικής οριζόντιας ή κατακόρυφης θέσης
linktitle: Ορισμός σχετικής οριζόντιας ή κατακόρυφης θέσης
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ορίζετε τη σχετική οριζόντια ή κάθετη θέση ενός πίνακα σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να ορίζουμε τη σχετική οριζόντια ή κάθετη θέση ενός πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Μέχρι το τέλος αυτού του σεμιναρίου, θα μπορείτε να ορίσετε τη σχετική οριζόντια ή κάθετη θέση του τραπεζιού σας στα έγγραφα του Word.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Φόρτωση του εγγράφου
Για να ξεκινήσετε την επεξεργασία λέξεων με το έγγραφο, ακολουθήστε τα εξής βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Φορτώστε το έγγραφο
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας και να δώσετε το σωστό όνομα αρχείου.

## Βήμα 3: Ρύθμιση της σχετικής θέσης του πίνακα
Στη συνέχεια, θα ορίσουμε τη σχετική οριζόντια ή κάθετη θέση του πίνακα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
// Ανακτήστε τον πίνακα
Table table = doc.FirstSection.Body.Tables[0];

//Ορισμός της σχετικής οριζόντιας θέσης του πίνακα
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Καθορίστε τη σχετική κατακόρυφη θέση του πίνακα
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Εδώ χρησιμοποιούμε το έγγραφο για να ανακτήσουμε τον πρώτο πίνακα από το σώμα της πρώτης ενότητας. Στη συνέχεια, ορίζουμε τη σχετική οριζόντια θέση του πίνακα με το`HorizontalAnchor` ιδιοκτησία που χρησιμοποιεί το`RelativeHorizontalPosition.Column` αξία. Ομοίως, ορίζουμε τη σχετική κατακόρυφη θέση του πίνακα με το`VerticalAnchor` ιδιοκτησία που χρησιμοποιεί το`RelativeVerticalPosition.Page` αξία.

## Βήμα 4: Αποθήκευση του τροποποιημένου εγγράφου
Τέλος, πρέπει να αποθηκεύσουμε το τροποποιημένο έγγραφο με καθορισμένη τη σχετική θέση του πίνακα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για το έγγραφο εξόδου.

### Δείγμα πηγαίου κώδικα για Ορισμός σχετικής οριζόντιας ή κατακόρυφης θέσης χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να ορίζουμε τη σχετική οριζόντια ή κάθετη θέση ενός πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να εφαρμόσετε αυτή τη σχετική θέση στους πίνακές σας στα έγγραφα του Word.