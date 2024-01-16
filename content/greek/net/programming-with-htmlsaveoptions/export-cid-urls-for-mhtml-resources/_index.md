---
title: Εξαγωγή Cid Urls για πόρους Mhtml
linktitle: Εξαγωγή Cid Urls για πόρους Mhtml
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την εξαγωγή διευθύνσεων URL CID πόρων MHTML κατά την αποθήκευση ενός εγγράφου με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για την εξαγωγή διευθύνσεων URL CID για πόρους MHTML με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να εξάγετε διευθύνσεις URL CID πόρων MHTML κατά την αποθήκευση ενός εγγράφου σε μορφή MHTML.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο για εξαγωγή. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο από έναν καθορισμένο κατάλογο:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`Document` φορτώνοντας το έγγραφο από τον καθορισμένο κατάλογο.

## Βήμα 3: Διαμόρφωση επιλογών δημιουργίας αντιγράφων ασφαλείας HTML

Τώρα θα διαμορφώσουμε τις επιλογές αποθήκευσης HTML για εξαγωγή διευθύνσεων URL CID πόρων MHTML. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`HtmlSaveOptions` με τη μορφή αποθήκευσης σε MHTML. Επιτρέπει επίσης την εξαγωγή διευθύνσεων URL CID πόρων MHTML με ρύθμιση`ExportCidUrlsForMhtmlResources` προς την`true`.

## Βήμα 4: Μετατροπή και αποθήκευση του εγγράφου σε MHTML

Τέλος, θα μετατρέψουμε το έγγραφο σε MHTML χρησιμοποιώντας τις επιλογές αποθήκευσης HTML που διαμορφώθηκαν νωρίτερα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Αυτός ο κώδικας μετατρέπει το έγγραφο σε MHTML και το αποθηκεύει σε αρχείο με τις διευθύνσεις URL CID των εξαγόμενων πόρων MHTML.

### Παράδειγμα πηγαίου κώδικα για Εξαγωγή Cid Urls για πόρους Mhtml χρησιμοποιώντας Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο εγγράφων στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να εξάγετε διευθύνσεις URL CID πόρων MHTML κατά την αποθήκευση ενός εγγράφου σε μορφή MHTML χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε να διαχειριστείτε εύκολα τις διευθύνσεις URL CID στα εξαγόμενα έγγραφα MHTML.

