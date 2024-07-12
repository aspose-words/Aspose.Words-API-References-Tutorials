---
title: Ρύθμιση σελίδας ρύθμισης και μορφοποίησης ενότητας
linktitle: Ρύθμιση σελίδας ρύθμισης και μορφοποίησης ενότητας
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη ρύθμιση της διάταξης και της μορφοποίησης ενότητας ενός εγγράφου με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να ρυθμίσετε τη διάταξη και τη μορφοποίηση ενότητας με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ορίσετε τον προσανατολισμό της σελίδας, τα περιθώρια και το μέγεθος χαρτιού.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Δημιουργία του εγγράφου

Σε αυτό το βήμα, θα δημιουργήσουμε ένα νέο έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα για να δημιουργήσετε το έγγραφο και να αρχικοποιήσετε τον κατασκευαστή:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου θέλετε να αποθηκεύσετε το έγγραφο.

## Βήμα 3: Ρύθμιση της διάταξης και αποθήκευση εγγράφου

Τώρα ας διαμορφώσουμε τη διάταξη του εγγράφου. Χρησιμοποιήστε τον ακόλουθο κώδικα για να ορίσετε τον προσανατολισμό, τα περιθώρια και το μέγεθος χαρτιού:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Αυτός ο κώδικας θα ορίσει τον προσανατολισμό της σελίδας σε οριζόντιο προσανατολισμό, το αριστερό περιθώριο σε 50 και το μέγεθος χαρτιού σε 10x14.

### Παράδειγμα πηγαίου κώδικα για Set Page Setup and Section Formatting με χρήση Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να διαμορφώνετε τη διάταξη και τη μορφοποίηση ενότητας ενός εγγράφου χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να προσαρμόσετε τη διάταξη και τη μορφοποίηση των δικών σας εγγράφων.