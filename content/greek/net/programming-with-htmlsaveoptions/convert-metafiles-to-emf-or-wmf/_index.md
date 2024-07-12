---
title: Μετατροπή Μετα-αρχείων σε Emf ή Wmf
linktitle: Μετατροπή Μετα-αρχείων σε Emf ή Wmf
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη μετατροπή μετα-αρχείων σε μορφές EMF ή WMF κατά τη μετατροπή ενός εγγράφου σε HTML με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να μετατρέψετε μετα-αρχεία σε μορφή EMF ή WMF με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να μετατρέπετε εικόνες σε μορφή μετα-αρχείου σε πιο συμβατές μορφές όπως EMF ή WMF κατά τη μετατροπή ενός εγγράφου σε HTML.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Εισαγωγή εικόνας στο έγγραφο

Σε αυτό το βήμα, θα εισαγάγουμε μια εικόνα στο έγγραφο που πρόκειται να μετατραπεί. Χρησιμοποιήστε τον ακόλουθο κώδικα για να εισαγάγετε μια εικόνα από μια πηγή δεδομένων χρησιμοποιώντας μια ετικέτα HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`Document`και`DocumentBuilder` για τη δημιουργία του εγγράφου. Εισάγει ένα`<img>` προσθέστε ετικέτα στο έγγραφο με μια κωδικοποιημένη εικόνα base64.

## Βήμα 3: Ορίστε τις επιλογές αποθήκευσης HTML

Τώρα θα ορίσουμε τις επιλογές αποθήκευσης HTML, συμπεριλαμβανομένης της μορφής μετα-αρχείου που θα χρησιμοποιείται για τις εικόνες. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`HtmlSaveOptions` και σετ`MetafileFormat` προς την`HtmlMetafileFormat.EmfOrWmf` για να καθορίσετε ότι τα μετα-αρχεία θα πρέπει να μετατρέπονται σε μορφή EMF ή WMF κατά τη μετατροπή σε HTML.

## Βήμα 4: Μετατροπή και αποθήκευση του εγγράφου σε HTML

Τέλος, θα μετατρέψουμε το έγγραφο σε HTML χρησιμοποιώντας τις επιλογές αποθήκευσης HTML που ορίσαμε προηγουμένως. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Αυτός ο κώδικας μετατρέπει το έγγραφο σε HTML και το αποθηκεύει σε αρχείο με τα μετα-αρχεία που έχουν μετατραπεί σε μορφή EMF ή WMF ανάλογα με το σύνολο των επιλογών αποθήκευσης.

### Παράδειγμα πηγαίου κώδικα για Μετατροπή μετα-αρχείων σε Emf ή Wmf χρησιμοποιώντας Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο εγγράφων στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να μετατρέπετε μετα-αρχεία σε μορφές EMF ή WMF όταν μετατρέπετε ένα έγγραφο σε HTML χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να διαχειριστείτε μετα-αρχεία στα έγγραφα HTML που έχετε μετατρέψει.