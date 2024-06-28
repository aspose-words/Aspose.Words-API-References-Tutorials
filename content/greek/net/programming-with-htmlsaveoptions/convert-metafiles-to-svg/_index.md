---
title: Μετατροπή Μετα-αρχείων σε Svg
linktitle: Μετατροπή Μετα-αρχείων σε Svg
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη μετατροπή μετα-αρχείων σε μορφή SVG κατά τη μετατροπή ενός εγγράφου σε HTML με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να μετατρέψετε μετα-αρχεία σε μορφή SVG με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να μετατρέπετε μετα-αρχεία σε μορφή SVG κατά τη μετατροπή ενός εγγράφου σε HTML.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Εισαγωγή εικόνας SVG στο έγγραφο

Σε αυτό το βήμα, θα εισαγάγουμε μια εικόνα SVG στο έγγραφο που πρόκειται να μετατραπεί. Χρησιμοποιήστε τον ακόλουθο κώδικα για να εισαγάγετε μια εικόνα SVG χρησιμοποιώντας μια ετικέτα HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`Document` και`DocumentBuilder` για τη δημιουργία του εγγράφου. Εισάγει α`<svg>` ετικέτα που περιέχει α`<polygon>` στοιχείο με χαρακτηριστικά για τον καθορισμό του σχήματος και του στυλ της εικόνας SVG.

## Βήμα 3: Ορίστε τις επιλογές αποθήκευσης HTML

Τώρα θα ορίσουμε τις επιλογές αποθήκευσης HTML, προσδιορίζοντας ότι τα μετααρχεία θα πρέπει να μετατραπούν σε μορφή SVG. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`HtmlSaveOptions` και σετ`MetafileFormat` προς την`HtmlMetafileFormat.Svg` για να καθορίσετε ότι τα μετα-αρχεία θα πρέπει να μετατρέπονται σε μορφή SVG κατά τη μετατροπή σε HTML.

## Βήμα 4: Μετατροπή και αποθήκευση του εγγράφου σε HTML

Τέλος, θα μετατρέψουμε το έγγραφο σε HTML χρησιμοποιώντας τις επιλογές αποθήκευσης HTML που καθορίστηκαν προηγουμένως. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Αυτός ο κώδικας μετατρέπει το έγγραφο σε HTML και το αποθηκεύει σε αρχείο με τα μετα-αρχεία να έχουν μετατραπεί σε SVG.

### Παράδειγμα πηγαίου κώδικα για Μετατροπή μετα-αρχείων σε Svg χρησιμοποιώντας Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
