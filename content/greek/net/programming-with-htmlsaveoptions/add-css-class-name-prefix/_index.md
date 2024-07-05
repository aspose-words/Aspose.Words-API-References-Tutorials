---
title: Προσθήκη προθέματος ονόματος κλάσης Css
linktitle: Προσθήκη προθέματος ονόματος κλάσης Css
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την προσθήκη ενός προθέματος ονόματος κλάσης CSS κατά τη μετατροπή ενός εγγράφου σε HTML με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να προσθέσετε ένα πρόθεμα ονόματος κλάσης CSS με Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να προσθέτετε ένα προσαρμοσμένο πρόθεμα σε ονόματα κλάσεων CSS που δημιουργούνται κατά τη μετατροπή ενός εγγράφου σε HTML.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word που θέλουμε να μετατρέψουμε σε HTML. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Ορίστε τις επιλογές αποθήκευσης HTML

Τώρα ας ορίσουμε τις επιλογές αποθήκευσης HTML, συμπεριλαμβανομένου του τύπου φύλλου στυλ CSS και του προθέματος ονόματος κλάσης CSS. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`HtmlSaveOptions` και σετ`CssStyleSheetType` προς την`CssStyleSheetType.External`για να δημιουργήσετε ένα εξωτερικό φύλλο στυλ CSS και`CssClassNamePrefix` προς την`"pfx_"` στο πρόθεμα`"pfx_"` σε ονόματα κλάσης CSS.

## Βήμα 4: Μετατροπή και αποθήκευση του εγγράφου σε HTML

Τέλος, θα μετατρέψουμε το έγγραφο σε HTML χρησιμοποιώντας τις επιλογές αποθήκευσης HTML που καθορίστηκαν προηγουμένως. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Αυτός ο κώδικας μετατρέπει το έγγραφο σε HTML και το αποθηκεύει σε αρχείο με το πρόθεμα ονόματος κλάσης CSS να έχει προστεθεί.

### Παράδειγμα πηγαίου κώδικα για Προσθήκη προθέματος ονόματος κλάσης Css χρησιμοποιώντας Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να προσθέτετε ένα πρόθεμα ονόματος κλάσης CSS κατά τη μετατροπή ενός εγγράφου σε HTML χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας το βήμα προς βήμα οδηγό που παρέχεται σε αυτό το σεμινάριο, μπορείτε να προσαρμόσετε τα ονόματα κλάσεων CSS στα έγγραφα HTML που έχετε μετατρέψει.