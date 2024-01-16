---
title: Επίλυση ονομάτων γραμματοσειρών
linktitle: Επίλυση ονομάτων γραμματοσειρών
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την επίλυση ονομάτων γραμματοσειρών που λείπουν κατά τη μετατροπή σε HTML με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlsaveoptions/resolve-font-names/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να επιλύσετε τα ονόματα γραμματοσειρών που λείπουν με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να επιλύετε αυτόματα τα ονόματα γραμματοσειρών που λείπουν κατά τη μετατροπή ενός εγγράφου σε HTML.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο προς επεξεργασία. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο από έναν καθορισμένο κατάλογο:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`Document` φορτώνοντας το έγγραφο από τον καθορισμένο κατάλογο.

## Βήμα 3: Διαμόρφωση επιλογών δημιουργίας αντιγράφων ασφαλείας HTML

Τώρα θα διαμορφώσουμε τις επιλογές αποθήκευσης HTML για την επίλυση ονομάτων γραμματοσειρών που λείπουν κατά τη μετατροπή. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`HtmlSaveOptions`και ορίζει το`ResolveFontNames` επιλογή να`true`για την επίλυση ονομάτων γραμματοσειρών που λείπουν κατά τη μετατροπή σε HTML. Επίσης το`PrettyFormat` η επιλογή έχει οριστεί σε`true` για να λάβετε σωστά μορφοποιημένο κώδικα HTML.

## Βήμα 4: Μετατροπή και αποθήκευση του εγγράφου σε HTML

Τέλος, θα μετατρέψουμε το έγγραφο σε HTML χρησιμοποιώντας τις επιλογές αποθήκευσης HTML που διαμορφώθηκαν νωρίτερα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Αυτός ο κώδικας μετατρέπει το έγγραφο σε HTML επιλύοντας αυτόματα τα ονόματα γραμματοσειρών που λείπουν και αποθηκεύει το αρχείο HTML που έχει μετατραπεί στον καθορισμένο κατάλογο.

### Παράδειγμα πηγαίου κώδικα για Επίλυση ονομάτων γραμματοσειρών χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο εγγράφων στο`dataDir` μεταβλητός.