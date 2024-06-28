---
title: Αριθμήστε Ιδιότητες
linktitle: Αριθμήστε Ιδιότητες
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την απαρίθμηση ιδιοτήτων εγγράφου με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-properties/enumerate-properties/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα της C# για να απαριθμήσετε ιδιότητες εγγράφου με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να έχετε πρόσβαση σε ενσωματωμένες και προσαρμοσμένες ιδιότητες ενός εγγράφου.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word του οποίου οι ιδιότητες θέλουμε να παραθέσουμε. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Αριθμός ιδιοτήτων

Τώρα ας παραθέσουμε τις ιδιότητες του εγγράφου, τόσο τις ενσωματωμένες όσο και τις προσαρμοσμένες ιδιότητες. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Αυτός ο κωδικός εμφανίζει το όνομα του εγγράφου και, στη συνέχεια, παραθέτει τις ενσωματωμένες και προσαρμοσμένες ιδιότητες που εμφανίζουν το όνομα και την αξία τους.

### Παράδειγμα πηγαίου κώδικα για την απαρίθμηση ιδιοτήτων χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να απαριθμείτε ιδιότητες εγγράφου χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να αποκτήσετε πρόσβαση και να προβάλετε τις ιδιότητες των δικών σας εγγράφων.

