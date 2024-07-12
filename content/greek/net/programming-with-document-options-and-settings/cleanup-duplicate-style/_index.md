---
title: Εκκαθάριση διπλότυπου στυλ
linktitle: Εκκαθάριση διπλότυπου στυλ
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τον καθαρισμό διπλότυπων στυλ σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Περιλαμβάνεται πλήρης πηγαίος κώδικας.
type: docs
weight: 10
url: /el/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα στον πηγαίο κώδικα C# για να καθαρίσετε διπλότυπα στυλ με το Aspose.Words για .NET. Αυτή η δυνατότητα βοηθά στην κατάργηση των διπλότυπων στυλ από ένα έγγραφο.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word που θέλουμε να καθαρίσουμε. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Μετρήστε τα στυλ πριν τον καθαρισμό

Πριν προχωρήσουμε στον καθαρισμό, θα μετρήσουμε τον αριθμό των στυλ που υπάρχουν στο έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα για να εμφανίσετε τον αριθμό στυλ:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Αυτή η δήλωση εμφανίζει τον αριθμό των στυλ που υπάρχουν στο έγγραφο.

## Βήμα 4: Εκκαθάριση διπλότυπων στυλ

Τώρα ας καθαρίσουμε τα διπλότυπα στυλ από το έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα για να εκτελέσετε τον καθαρισμό:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Αυτός ο κώδικας καθαρίζει τα διπλότυπα στυλ από το έγγραφο χρησιμοποιώντας τις καθορισμένες επιλογές. Σε αυτό το παράδειγμα, ενεργοποιήσαμε το`DuplicateStyle` επιλογή καθαρισμού διπλότυπων στυλ.

## Βήμα 5: Μετρήστε τα στυλ μετά τον καθαρισμό

Αφού κάνουμε τον καθαρισμό, θα μετρήσουμε ξανά τον αριθμό των στυλ για να ελέγξουμε αν έχει μειωθεί. Χρησιμοποιήστε τον ακόλουθο κώδικα για να εμφανίσετε τον αριθμό των νέων στυλ:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Αυτή η δήλωση εμφανίζει τον αριθμό των στυλ που απομένουν μετά τον καθαρισμό.

### Παράδειγμα πηγαίου κώδικα για Εκκαθάριση διπλότυπου στυλ χρησιμοποιώντας Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Πλήθος στυλ πριν από τον Καθαρισμό.
	Console.WriteLine(doc.Styles.Count);

	// Καθαρίζει διπλότυπα στυλ από το έγγραφο.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// Ο αριθμός των στυλ μετά την Εκκαθάριση μειώθηκε.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```