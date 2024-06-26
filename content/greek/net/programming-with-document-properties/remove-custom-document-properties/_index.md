---
title: Καταργήστε τις ιδιότητες προσαρμοσμένου εγγράφου
linktitle: Καταργήστε τις ιδιότητες προσαρμοσμένου εγγράφου
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την κατάργηση προσαρμοσμένων ιδιοτήτων από ένα έγγραφο με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-properties/remove-custom-document-properties/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να καταργήσετε προσαρμοσμένες ιδιότητες από ένα έγγραφο με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να αφαιρέσετε μια συγκεκριμένη προσαρμοσμένη ιδιότητα από ένα έγγραφο.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word από το οποίο θέλουμε να καταργήσουμε τις προσαρμοσμένες ιδιότητες. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Διαγραφή προσαρμοσμένων ιδιοτήτων

Τώρα ας αφαιρέσουμε μια συγκεκριμένη προσαρμοσμένη ιδιότητα από το έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Αυτός ο κωδικός καταργεί την προσαρμοσμένη ιδιότητα "Εξουσιοδοτημένη ημερομηνία" από το έγγραφο. Μπορείτε να αντικαταστήσετε το "Authorized Date" με το όνομα της προσαρμοσμένης ιδιότητας που θέλετε να καταργήσετε.

### Παράδειγμα πηγαίου κώδικα για Κατάργηση προσαρμοσμένων ιδιοτήτων εγγράφου χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να αφαιρείτε προσαρμοσμένες ιδιότητες από ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να αφαιρέσετε προσαρμοσμένες ιδιότητες από τα δικά σας έγγραφα.