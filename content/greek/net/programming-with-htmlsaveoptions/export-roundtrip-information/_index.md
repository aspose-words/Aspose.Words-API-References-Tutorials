---
title: Εξαγωγή πληροφοριών μετ' επιστροφής
linktitle: Εξαγωγή πληροφοριών μετ' επιστροφής
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την εξαγωγή πληροφοριών μετ' επιστροφής κατά την αποθήκευση ενός εγγράφου ως HTML με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να εξάγετε πληροφορίες μετ' επιστροφής από ένα έγγραφο με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να συμπεριλάβετε πληροφορίες μετ' επιστροφής στο εξαγόμενο αρχείο HTML, διευκολύνοντας την ανάκτηση των αλλαγών που έγιναν στο αρχικό έγγραφο.

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

Τώρα θα διαμορφώσουμε τις επιλογές αποθήκευσης HTML για την εξαγωγή των πληροφοριών μετ' επιστροφής του εγγράφου. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Αυτός ο κώδικας δημιουργεί μια παρουσία του`HtmlSaveOptions`και ορίζει το`ExportRoundtripInformation` επιλογή να`true` να περιλαμβάνει πληροφορίες μετ' επιστροφής κατά την εξαγωγή.

## Βήμα 4: Μετατροπή και αποθήκευση του εγγράφου σε HTML

Τέλος, θα μετατρέψουμε το έγγραφο σε HTML χρησιμοποιώντας τις επιλογές αποθήκευσης HTML που διαμορφώθηκαν νωρίτερα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Αυτός ο κώδικας μετατρέπει το έγγραφο σε HTML, συμπεριλαμβανομένων των πληροφοριών μετ' επιστροφής, και αποθηκεύει το εξαγόμενο αρχείο HTML στον καθορισμένο κατάλογο.

### Παράδειγμα πηγαίου κώδικα για Εξαγωγή πληροφοριών μετ' επιστροφής με χρήση του Aspose.Words για .NET


```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο εγγράφων στο`dataDir` μεταβλητός.