---
title: Μορφή 1 Bpp Indexed
linktitle: Μορφή 1 Bpp Indexed
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να μορφοποιείτε εικόνες σε 1 bpp με ευρετήριο με το Aspose.Words για .NET. Πλήρες σεμινάριο για εικόνες χαμηλού βάθους χρώματος.
type: docs
weight: 10
url: /el/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον πηγαίο κώδικα C# που παρέχεται για τη λειτουργία "Format 1Bpp Indexed" με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να μορφοποιείτε εικόνες σε ένα έγγραφο σε μορφή PNG με βάθος χρώματος 1 bit ανά pixel (1 bpp) και λειτουργία ευρετηρίου χρώματος.

## Βήμα 1: Ρύθμιση περιβάλλοντος

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ρυθμίσει το περιβάλλον ανάπτυξης με το Aspose.Words για .NET. Βεβαιωθείτε ότι έχετε προσθέσει τις απαραίτητες αναφορές και έχετε εισαγάγει τους κατάλληλους χώρους ονομάτων.

## Βήμα 2: Φόρτωση του εγγράφου

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Σε αυτό το βήμα, φορτώνουμε το έγγραφο χρησιμοποιώντας το`Document` μέθοδο και περνώντας τη διαδρομή προς το αρχείο DOCX για φόρτωση.

## Βήμα 3: Διαμορφώστε τις επιλογές δημιουργίας αντιγράφων ασφαλείας εικόνας

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Σε αυτό το βήμα, διαμορφώνουμε τις επιλογές δημιουργίας αντιγράφων ασφαλείας για εικόνες. Δημιουργούμε ένα νέο`ImageSaveOptions`αντικείμενο που καθορίζει την επιθυμητή μορφή αποθήκευσης, εδώ "Png" για τη μορφή PNG. Επίσης, ορίζουμε τη σελίδα που θα συμπεριληφθεί στην εικόνα, τη λειτουργία ασπρόμαυρου χρώματος και τη μορφή εικονοστοιχείου με ευρετήριο 1 bpp.

## Βήμα 4: Δημιουργία αντιγράφων ασφαλείας εικόνων

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 Σε αυτό το τελευταίο βήμα, αποθηκεύουμε τις εικόνες του εγγράφου σε μορφή PNG χρησιμοποιώντας το`Save` μέθοδο και μεταβίβαση της διαδρομής προς το αρχείο εξόδου, μαζί με τις καθορισμένες επιλογές αποθήκευσης.

Τώρα μπορείτε να εκτελέσετε τον πηγαίο κώδικα για να μορφοποιήσετε τις εικόνες του εγγράφου σε μορφή PNG με βάθος χρώματος 1 bpp με ευρετήριο. Το αρχείο που προκύπτει θα αποθηκευτεί στον καθορισμένο κατάλογο με το όνομα "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Δείγμα πηγαίου κώδικα για Μορφή 1 Bpp Ευρετηριασμένο με χρήση Aspose.Words για .NET

```csharp 
 
			 // Διαδρομή στον κατάλογο εγγράφων σας
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε τη δυνατότητα μορφής Indexed 1 Bpp με το Aspose.Words για .NET. Μάθαμε πώς να μορφοποιούμε εικόνες σε ένα έγγραφο σε μορφή PNG με βάθος χρώματος 1 bit ανά pixel (1 bpp) και λειτουργία ευρετηρίου χρώματος.

Αυτή η δυνατότητα είναι χρήσιμη όταν θέλετε να λάβετε εικόνες με χαμηλό βάθος χρώματος και μικρό μέγεθος αρχείου. Η μορφή Indexed 1 Bpp επιτρέπει την αναπαράσταση των εικόνων χρησιμοποιώντας μια ευρετηριασμένη χρωματική παλέτα, η οποία μπορεί να είναι ευεργετική για ορισμένες συγκεκριμένες εφαρμογές.

Το Aspose.Words for .NET προσφέρει ένα ευρύ φάσμα προηγμένων δυνατοτήτων για χειρισμό και δημιουργία εγγράφων. Η μορφή 1 Bpp Indexed είναι ένα από τα πολλά ισχυρά εργαλεία που θέτει στη διάθεσή σας.