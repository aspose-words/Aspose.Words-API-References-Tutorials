---
title: Διατηρήστε τους χαρακτήρες ελέγχου παλαιού τύπου
linktitle: Διατηρήστε τους χαρακτήρες ελέγχου παλαιού τύπου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να διατηρείτε χαρακτήρες ελέγχου παλαιού τύπου κατά την αποθήκευση ενός εγγράφου με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον παρεχόμενο πηγαίο κώδικα C# για να διατηρήσουμε τους χαρακτήρες ελέγχου παλαιού τύπου κατά την αποθήκευση ενός εγγράφου χρησιμοποιώντας το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να διατηρείτε ειδικούς χαρακτήρες ελέγχου κατά τη μετατροπή ή την αποθήκευση ενός εγγράφου.

## Βήμα 1: Ρύθμιση περιβάλλοντος

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ρυθμίσει το περιβάλλον ανάπτυξης με το Aspose.Words για .NET. Βεβαιωθείτε ότι έχετε προσθέσει τις απαραίτητες αναφορές και έχετε εισαγάγει τους κατάλληλους χώρους ονομάτων.

## Βήμα 2: Φόρτωση του εγγράφου

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Σε αυτό το βήμα, φορτώνουμε το έγγραφο χρησιμοποιώντας το`Document` μέθοδο και μεταβίβαση της διαδρομής στο αρχείο που περιέχει τους κληρονομικούς χαρακτήρες ελέγχου.

## Βήμα 3: Διαμόρφωση επιλογών δημιουργίας αντιγράφων ασφαλείας OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 Σε αυτό το βήμα, διαμορφώνουμε τις επιλογές αποθήκευσης OOXML δημιουργώντας μια νέα`OoxmlSaveOptions` αντικείμενο. Καθορίζουμε την επιθυμητή μορφή αποθήκευσης (εδώ,`FlatOpc` ) και ενεργοποιήστε το`KeepLegacyControlChars` επιλογή διατήρησης χαρακτήρων ελέγχου παλαιού τύπου.

## Βήμα 4: Αποθήκευση του εγγράφου με χαρακτήρες ελέγχου παλαιού τύπου

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Σε αυτό το τελευταίο βήμα, αποθηκεύουμε το έγγραφο χρησιμοποιώντας το`Save` μέθοδο και περνώντας τη διαδρομή προς το αρχείο εξόδου με το`.docx` επέκταση, μαζί με τις καθορισμένες επιλογές αποθήκευσης.

Τώρα μπορείτε να εκτελέσετε τον πηγαίο κώδικα για να διατηρήσετε τους χαρακτήρες ελέγχου παλαιού τύπου κατά την αποθήκευση ενός εγγράφου. Το αρχείο που προκύπτει θα αποθηκευτεί στον καθορισμένο κατάλογο με το όνομα "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Δείγμα πηγαίου κώδικα για το Keep Legacy Control Chars χρησιμοποιώντας το Aspose.Words για .NET 
```csharp

// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε τη λειτουργικότητα της διατήρησης χαρακτήρων ελέγχου παλαιού τύπου κατά την αποθήκευση ενός εγγράφου χρησιμοποιώντας το Aspose.Words για .NET. Μάθαμε πώς να διατηρούμε αυτούς τους ειδικούς χαρακτήρες που μπορεί να είναι σημαντικοί για τη σωστή μορφοποίηση ή εμφάνιση του εγγράφου.

 Η διατήρηση χαρακτήρων ελέγχου παλαιού τύπου είναι ιδιαίτερα χρήσιμη κατά την επεξεργασία λέξεων με έγγραφα που χρησιμοποιούν παλαιότερα ή συγκεκριμένα χαρακτηριστικά, όπως ειδικούς χαρακτήρες ελέγχου. Ενεργοποιώντας το`KeepLegacyControlChars` επιλογή κατά την αποθήκευση του εγγράφου, διασφαλίζετε ότι αυτοί οι χαρακτήρες διατηρούνται.

Το Aspose.Words for .NET προσφέρει μια σειρά από ευέλικτες και ισχυρές επιλογές δημιουργίας αντιγράφων ασφαλείας για να καλύψει τις ανάγκες χειρισμού εγγράφων σας. Χρησιμοποιώντας τις κατάλληλες επιλογές, μπορείτε να προσαρμόσετε τη διαδικασία δημιουργίας αντιγράφων ασφαλείας για να διατηρήσετε τα συγκεκριμένα χαρακτηριστικά των εγγράφων σας.

Μη διστάσετε να ενσωματώσετε αυτήν τη λειτουργία στα έργα σας Aspose.Words για .NET για να διασφαλίσετε την ακεραιότητα και τη διατήρηση των χαρακτήρων ελέγχου παλαιού τύπου στα έγγραφά σας.