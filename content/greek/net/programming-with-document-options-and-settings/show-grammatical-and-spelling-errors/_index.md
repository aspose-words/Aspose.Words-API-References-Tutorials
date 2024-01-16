---
title: Εμφάνιση γραμματικών και ορθογραφικών λαθών
linktitle: Εμφάνιση γραμματικών και ορθογραφικών λαθών
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την ενεργοποίηση της εμφάνισης γραμματικών και ορθογραφικών λαθών σε ένα έγγραφο με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να ενεργοποιήσετε την εμφάνιση γραμματικών και ορθογραφικών λαθών με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να βλέπετε γραμματικά και ορθογραφικά λάθη σε ένα έγγραφο.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word για το οποίο θέλουμε να εμφανίσουμε γραμματικά και ορθογραφικά λάθη. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Ενεργοποίηση εμφάνισης σφαλμάτων

Τώρα θα ενεργοποιήσουμε την εμφάνιση γραμματικών και ορθογραφικών λαθών στο έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα για να ενεργοποιήσετε την εμφάνιση σφαλμάτων:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Αυτός ο κώδικας επιτρέπει την εμφάνιση γραμματικών λαθών (`ShowGrammaticalErrors`) και ορθογραφικά λάθη (`ShowSpellingErrors`) στο έγγραφο.

### Παράδειγμα πηγαίου κώδικα για Εμφάνιση γραμματικών και ορθογραφικών σφαλμάτων χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα μάθατε πώς να ενεργοποιείτε την εμφάνιση γραμματικών και ορθογραφικών λαθών σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να ενεργοποιήσετε αυτήν τη δυνατότητα στα δικά σας έγγραφα.