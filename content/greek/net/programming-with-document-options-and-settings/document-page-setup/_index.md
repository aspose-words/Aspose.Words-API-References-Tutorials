---
title: Ρύθμιση σελίδας εγγράφου
linktitle: Ρύθμιση σελίδας εγγράφου
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη ρύθμιση μιας διάταξης εγγράφου με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-options-and-settings/document-page-setup/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να διαμορφώσετε τη διάταξη εγγράφων με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ορίσετε τη λειτουργία διάταξης, τον αριθμό των χαρακτήρων ανά γραμμή και τον αριθμό των γραμμών ανά σελίδα.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word που θέλουμε να διαμορφώσουμε. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Ρύθμιση της διάταξης

Τώρα ας διαμορφώσουμε τη διάταξη του εγγράφου. Χρησιμοποιήστε τον ακόλουθο κώδικα για να ορίσετε τη λειτουργία διάταξης, τον αριθμό των χαρακτήρων ανά γραμμή και τον αριθμό γραμμών ανά σελίδα:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Αυτός ο κώδικας ορίζει τη λειτουργία διάταξης σε "Πλέγμα" και στη συνέχεια καθορίζει τον αριθμό των χαρακτήρων ανά γραμμή και τον αριθμό των γραμμών ανά σελίδα.

### Παράδειγμα πηγαίου κώδικα για τη ρύθμιση σελίδας εγγράφου χρησιμοποιώντας το Aspose.Words για .NET


```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Ρυθμίστε τη λειτουργία διάταξης για μια ενότητα που επιτρέπει τον καθορισμό της συμπεριφοράς του πλέγματος εγγράφων.
	// Σημειώστε ότι η καρτέλα Document Grid γίνεται ορατή στο παράθυρο διαλόγου Page Setup του MS Word.
	// εάν κάποια ασιατική γλώσσα ορίζεται ως γλώσσα επεξεργασίας.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να διαμορφώνετε τη διάταξη ενός εγγράφου χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να προσαρμόσετε τη διάταξη των δικών σας εγγράφων.