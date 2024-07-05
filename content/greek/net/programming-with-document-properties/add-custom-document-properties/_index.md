---
title: Προσθήκη προσαρμοσμένων ιδιοτήτων εγγράφου
linktitle: Προσθήκη προσαρμοσμένων ιδιοτήτων εγγράφου
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την προσθήκη προσαρμοσμένων ιδιοτήτων σε ένα έγγραφο με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-properties/add-custom-document-properties/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να προσθέσετε προσαρμοσμένες ιδιότητες σε ένα έγγραφο με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να προσθέσετε προσαρμοσμένες πληροφορίες στο έγγραφο.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word στο οποίο θέλουμε να προσθέσουμε προσαρμοσμένες ιδιότητες. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Προσθέστε προσαρμοσμένες ιδιότητες

Τώρα ας προσθέσουμε προσαρμοσμένες ιδιότητες στο έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα για να προσθέσετε τις ιδιότητες:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Αυτός ο κωδικός ελέγχει πρώτα εάν η ιδιότητα "Εξουσιοδοτημένο" υπάρχει ήδη στις προσαρμοσμένες ιδιότητες. Εάν υπάρχει, η διαδικασία διακόπτεται. Διαφορετικά, οι προσαρμοσμένες ιδιότητες προστίθενται στο έγγραφο.

### Παράδειγμα πηγαίου κώδικα για Προσθήκη προσαρμοσμένων ιδιοτήτων εγγράφου χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να προσθέτετε προσαρμοσμένες ιδιότητες σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να προσθέσετε τις δικές σας προσαρμοσμένες ιδιότητες στα έγγραφά σας.