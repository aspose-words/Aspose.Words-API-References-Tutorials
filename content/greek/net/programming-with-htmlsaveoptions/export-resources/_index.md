---
title: Εξαγωγή Πόρων
linktitle: Εξαγωγή Πόρων
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την εξαγωγή πόρων εγγράφων κατά την αποθήκευση ως HTML με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlsaveoptions/export-resources/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να εξάγετε πόρους εγγράφων με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να εξάγετε πόρους, όπως γραμματοσειρές, ως εξωτερικά αρχεία κατά την αποθήκευση ενός εγγράφου σε μορφή HTML.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο για εξαγωγή. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο από έναν καθορισμένο κατάλογο:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`Document` φορτώνοντας το έγγραφο από τον καθορισμένο κατάλογο.

## Βήμα 3: Διαμόρφωση επιλογών δημιουργίας αντιγράφων ασφαλείας HTML

Τώρα θα διαμορφώσουμε τις επιλογές αποθήκευσης HTML για την εξαγωγή των πόρων του εγγράφου. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`HtmlSaveOptions` και ορίζει τις ακόλουθες επιλογές:

- `CssStyleSheetType` Έχει οριστεί`CssStyleSheetType.External` για εξαγωγή του φύλλου στυλ CSS σε ένα εξωτερικό αρχείο.
- `ExportFontResources` Έχει οριστεί`true` για εξαγωγή πόρων γραμματοσειρών.
- `ResourceFolder` καθορίζει τον κατάλογο προορισμού όπου θα αποθηκευτούν οι πόροι.
- `ResourceFolderAlias`καθορίζει το ψευδώνυμο URL που θα χρησιμοποιηθεί για την πρόσβαση σε πόρους.

## Βήμα 4: Μετατροπή και αποθήκευση του εγγράφου σε HTML

Τέλος, θα μετατρέψουμε το έγγραφο σε HTML χρησιμοποιώντας τις επιλογές αποθήκευσης HTML που διαμορφώθηκαν νωρίτερα. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Αυτός ο κώδικας μετατρέπει το έγγραφο σε HTML και αποθηκεύει τους πόρους στον καθορισμένο κατάλογο, χρησιμοποιώντας το καθορισμένο ψευδώνυμο URL.

### Παράδειγμα πηγαίου κώδικα για Εξαγωγή πόρων με χρήση Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο εγγράφων στο`dataDir` μεταβλητός.