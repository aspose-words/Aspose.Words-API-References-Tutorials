---
title: Εξαγωγή πεδίου φόρμας εισαγωγής κειμένου ως κείμενο
linktitle: Εξαγωγή πεδίου φόρμας εισαγωγής κειμένου ως κείμενο
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την εξαγωγή πεδίων φόρμας εισαγωγής κειμένου ως απλό κείμενο με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να εξάγετε πεδία φόρμας εισαγωγής κειμένου ως απλό κείμενο με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να εξάγετε πεδία φόρμας εισαγωγής κειμένου ως αναγνώσιμο κείμενο, αντί να τα εξάγετε ως στοιχεία εισαγωγής HTML.

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

Τώρα θα διαμορφώσουμε τις επιλογές αποθήκευσης HTML για εξαγωγή πεδίων φόρμας εισαγωγής κειμένου ως απλό κείμενο. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Ο καθορισμένος φάκελος πρέπει να υπάρχει και να είναι κενός.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`HtmlSaveOptions`και ορίζει το`ExportTextInputFormFieldAsText` επιλογή να`true` για εξαγωγή πεδίων φόρμας εισαγωγής κειμένου ως απλό κείμενο. Επιπλέον, καθορίζει τον φάκελο στον οποίο θα αποθηκευτούν οι εξαγόμενες εικόνες.

## Βήμα 4: Μετατροπή και αποθήκευση του εγγράφου σε HTML

Τέλος, θα μετατρέψουμε το έγγραφο σε HTML χρησιμοποιώντας τις επιλογές αποθήκευσης HTML που διαμορφώθηκαν νωρίτερα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Αυτός ο κώδικας μετατρέπει το έγγραφο σε HTML εξάγοντας πεδία φόρμας εισαγωγής κειμένου ως απλό κείμενο και αποθηκεύει το εξαγόμενο αρχείο HTML στον καθορισμένο κατάλογο.

### Παράδειγμα πηγαίου κώδικα για εξαγωγή πεδίου φόρμας εισαγωγής κειμένου ως κείμενο χρησιμοποιώντας Aspose.Words για .NET


```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Ο καθορισμένος φάκελος πρέπει να υπάρχει και να είναι κενός.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Ορίστε μια επιλογή για εξαγωγή πεδίων φόρμας ως απλό κείμενο, όχι ως στοιχεία εισαγωγής HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο εγγράφων στο`dataDir` μεταβλητός.