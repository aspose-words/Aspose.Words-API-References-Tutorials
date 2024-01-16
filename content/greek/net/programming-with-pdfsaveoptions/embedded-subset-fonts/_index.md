---
title: Ενσωματώστε γραμματοσειρές υποσυνόλου σε έγγραφο PDF
linktitle: Ενσωματώστε γραμματοσειρές υποσυνόλου σε έγγραφο PDF
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την ενσωμάτωση υποσυνόλων γραμματοσειρών σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Αυτό το άρθρο παρέχει έναν οδηγό βήμα προς βήμα σχετικά με τον τρόπο χρήσης της δυνατότητας ενσωμάτωσης υποσυνόλου γραμματοσειρών με το Aspose.Words για .NET. Θα εξηγήσουμε λεπτομερώς κάθε μέρος του κώδικα. Στο τέλος αυτού του σεμιναρίου, θα μπορείτε να κατανοήσετε πώς να ενσωματώσετε υποσύνολα γραμματοσειρών σε ένα έγγραφο και να δημιουργήσετε ένα PDF που περιέχει μόνο τους γλυφούς που χρησιμοποιούνται στο έγγραφο.

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει τη βιβλιοθήκη Aspose.Words για .NET στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη και τις οδηγίες εγκατάστασης στον ιστότοπο Aspose.

## Βήμα 1: Ορίστε τον κατάλογο εγγράφων

 Για να ξεκινήσετε, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο όπου βρίσκονται τα έγγραφά σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Ανεβάστε το έγγραφο

Στη συνέχεια, πρέπει να φορτώσουμε το έγγραφο που θέλουμε να επεξεργαστούμε. Σε αυτό το παράδειγμα, υποθέτουμε ότι το έγγραφο ονομάζεται "Rendering.docx" και βρίσκεται στον καθορισμένο κατάλογο εγγράφων.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Βήμα 3: Διαμορφώστε τις επιλογές αποθήκευσης ως PDF

 Για να δημιουργήσουμε ένα PDF που περιέχει μόνο τα υποσύνολα γραμματοσειρών που χρησιμοποιούνται στο έγγραφο, πρέπει να ρυθμίσουμε τις παραμέτρους του`PdfSaveOptions` αντικείμενο με το`EmbedFullFonts` ιδιοκτησία ορίζεται σε`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Βήμα 4: Αποθηκεύστε το έγγραφο ως PDF με υποσύνολα γραμματοσειρών

 Τέλος, μπορούμε να αποθηκεύσουμε το έγγραφο ως PDF χρησιμοποιώντας τα υποσύνολα γραμματοσειρών. Καθορίστε το όνομα του αρχείου εξόδου και το`saveOptions` αντικείμενο που διαμορφώσαμε στο προηγούμενο βήμα.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Αυτό είναι όλο ! Έχετε ενσωματώσει με επιτυχία υποσύνολα γραμματοσειρών σε ένα έγγραφο και δημιουργήσατε ένα PDF που περιέχει μόνο τους γλυφούς που χρησιμοποιούνται στο έγγραφο με το Aspose.Words για .NET.

### Δείγμα πηγαίου κώδικα για την ενσωμάτωση υποσυνόλων γραμματοσειρών με το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Το PDF εξόδου θα περιέχει υποσύνολα των γραμματοσειρών στο έγγραφο.
	// Μόνο οι γλυφές που χρησιμοποιούνται στο έγγραφο περιλαμβάνονται στις γραμματοσειρές PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να ενσωματώνουμε υποσύνολα γραμματοσειρών σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.Words για .NET. Η ενσωμάτωση υποσυνόλων γραμματοσειρών βοηθά στη μείωση του μεγέθους του αρχείου PDF, διατηρώντας παράλληλα την εμφάνιση του εγγράφου χρησιμοποιώντας μόνο τους χαρακτήρες που χρησιμοποιούνται στην πραγματικότητα. Αυτό εξασφαλίζει καλύτερη συμβατότητα και απόδοση κατά την προβολή και την εκτύπωση του PDF. Μη διστάσετε να εξερευνήσετε περαιτέρω τις δυνατότητες του Aspose.Words για .NET για να βελτιστοποιήσετε τη δημιουργία των εγγράφων PDF σας με ενσωματωμένα υποσύνολα γραμματοσειρών.

### Συχνές Ερωτήσεις

#### Ε: Τι είναι η ενσωμάτωση υποσυνόλων γραμματοσειρών σε ένα έγγραφο PDF;
Α: Η ενσωμάτωση υποσυνόλων γραμματοσειρών σε ένα έγγραφο PDF είναι η διαδικασία συμπερίληψης μόνο των γλυφών που χρησιμοποιούνται στο έγγραφο, αντί να συμπεριλαμβάνονται όλες οι πλήρεις γραμματοσειρές. Αυτό μειώνει το μέγεθος του αρχείου PDF συμπεριλαμβάνοντας μόνο τα δεδομένα γραμματοσειράς που είναι απαραίτητα για την εμφάνιση των χαρακτήρων που χρησιμοποιούνται πραγματικά στο έγγραφο.

#### Ε: Ποια είναι η διαφορά μεταξύ της ενσωμάτωσης πλήρων γραμματοσειρών και της ενσωμάτωσης υποσυνόλων γραμματοσειρών;
Α: Η πλήρης ενσωμάτωση γραμματοσειράς σημαίνει ότι συμπεριλαμβάνονται όλες οι γραμματοσειρές που χρησιμοποιούνται στο έγγραφο στο αρχείο PDF, το οποίο διασφαλίζει ότι το έγγραφο θα εμφανίζεται ακριβώς όπως σχεδιάστηκε, αλλά μπορεί να αυξήσει το μέγεθος του αρχείου PDF. Αντίθετα, η ενσωμάτωση υποσυνόλων γραμματοσειρών περιέχει μόνο τους γλυφούς που χρησιμοποιούνται στο έγγραφο, μειώνοντας έτσι το μέγεθος του αρχείου PDF, αλλά περιορίζοντας τη δυνατότητα ακριβούς αναπαραγωγής της εμφάνισης του εγγράφου, εάν προστεθούν πρόσθετοι χαρακτήρες αργότερα.

#### Ε: Πώς μπορώ να ενσωματώσω υποσύνολα γραμματοσειρών σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.Words για .NET;
Α: Για να ενσωματώσετε υποσύνολα γραμματοσειρών σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.Words για .NET, ακολουθήστε τα εξής βήματα:

 Ορίστε τη διαδρομή καταλόγου εγγράφου αντικαθιστώντας`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή του καταλόγου των εγγράφων σας.

 Φορτώστε το έγγραφο που θέλετε να επεξεργαστείτε χρησιμοποιώντας το`Document` κλάση και τη διαδρομή του εγγράφου.

 Διαμορφώστε τις επιλογές αποθήκευσης PDF δημιουργώντας μια παρουσία του`PdfSaveOptions` τάξη και τη ρύθμιση του`EmbedFullFonts`ιδιοκτησία σε`false`Αυτό διασφαλίζει ότι μόνο τα υποσύνολα γραμματοσειρών που χρησιμοποιούνται στο έγγραφο θα συμπεριληφθούν στο αρχείο PDF.

 Αποθηκεύστε το έγγραφο σε μορφή PDF με τα υποσύνολα γραμματοσειράς ενσωματωμένα χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο, καθορίζοντας το όνομα του αρχείου εξόδου και τις επιλογές αποθήκευσης που διαμορφώθηκαν νωρίτερα.

#### Ε: Ποια είναι τα οφέλη από την ενσωμάτωση υποσυνόλων γραμματοσειρών σε ένα έγγραφο PDF;
Α: Τα οφέλη από την ενσωμάτωση υποσυνόλων γραμματοσειρών σε ένα έγγραφο PDF είναι:

Μειωμένο μέγεθος αρχείου PDF: Με τη συμπερίληψη μόνο των γλυφών που χρησιμοποιούνται στο έγγραφο, το μέγεθος του αρχείου PDF μειώνεται σε σύγκριση με την ενσωμάτωση πλήρους γραμματοσειράς.

Διατήρηση της εμφάνισης του εγγράφου: Τα υποσύνολα γραμματοσειρών που περιλαμβάνονται στο αρχείο PDF καθιστούν δυνατή την αναπαραγωγή της εμφάνισης του εγγράφου χρησιμοποιώντας μόνο τους χαρακτήρες που χρησιμοποιούνται στην πραγματικότητα.

Συμβατότητα με τους περιορισμούς της Άδειας χρήσης: Η ενσωμάτωση υποσυνόλων γραμματοσειρών μπορεί να προτιμάται σε περιπτώσεις όπου οι πλήρεις γραμματοσειρές δεν μπορούν να ενσωματωθούν νόμιμα λόγω περιορισμών αδειοδότησης.