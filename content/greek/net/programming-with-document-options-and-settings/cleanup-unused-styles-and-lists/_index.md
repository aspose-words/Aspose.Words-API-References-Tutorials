---
title: Εκκαθάριση αχρησιμοποίητων στυλ και λιστών
linktitle: Εκκαθάριση αχρησιμοποίητων στυλ και λιστών
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τον καθαρισμό αχρησιμοποίητων στυλ και λιστών σε ένα έγγραφο με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να καθαρίσετε αχρησιμοποίητα στυλ και λίστες με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να αφαιρέσετε στυλ και λίστες που δεν χρησιμοποιούνται σε ένα έγγραφο.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word που περιέχει τα αχρησιμοποίητα στυλ και λίστες που θέλουμε να καθαρίσουμε. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Μετρήστε στυλ και λίστες πριν τον καθαρισμό

Πριν από τον καθαρισμό, θα μετρήσουμε τον αριθμό των στυλ και των λιστών που υπάρχουν στο έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα για να εμφανίσετε τους μετρητές:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Αυτές οι οδηγίες δείχνουν τον αριθμό των στυλ και των λιστών που υπάρχουν στο έγγραφο πριν από τον καθαρισμό.

## Βήμα 4: Εκκαθάριση στυλ και λιστών που δεν χρησιμοποιούνται

Τώρα ας καθαρίσουμε τα αχρησιμοποίητα στυλ και λίστες από το έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα για να εκτελέσετε τον καθαρισμό:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Αυτός ο κώδικας καθαρίζει αχρησιμοποίητα στυλ και λίστες από το έγγραφο χρησιμοποιώντας τις καθορισμένες επιλογές. Σε αυτό το παράδειγμα, ενεργοποιήσαμε το`UnusedStyles` επιλογή για κατάργηση αχρησιμοποίητων στυλ και απενεργοποίηση του`UnusedLists` επιλογή διατήρησης των λιστών ακόμα κι αν δεν χρησιμοποιούνται.

## Βήμα 5: Μετρήστε στυλ και λίστες μετά τον καθαρισμό

Αφού κάνουμε την εκκαθάριση, θα μετρήσουμε ξανά τα στυλ και τις λίστες για να ελέγξουμε αν έχουν συμπτύξει. Χρησιμοποιήστε τον ακόλουθο κώδικα για να εμφανίσετε τους νέους μετρητές:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Αυτές οι οδηγίες δείχνουν τον αριθμό των στυλ και των λιστών που απομένουν μετά τον καθαρισμό.

### Παράδειγμα πηγαίου κώδικα για Εκκαθάριση αχρησιμοποίητων στυλ και λιστών χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Σε συνδυασμό με τα ενσωματωμένα στυλ, το έγγραφο έχει πλέον οκτώ στυλ.
	// Ένα προσαρμοσμένο στυλ επισημαίνεται ως "χρησιμοποιημένο" ενώ υπάρχει οποιοδήποτε κείμενο μέσα στο έγγραφο
	// μορφοποιημένο σε αυτό το στυλ. Αυτό σημαίνει ότι τα 4 στυλ που προσθέσαμε δεν χρησιμοποιούνται αυτήν τη στιγμή.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Καθαρίζει αχρησιμοποίητα στυλ και λίστες από το έγγραφο ανάλογα με τις δεδομένες Επιλογές Cleanup.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να καθαρίζετε αχρησιμοποίητα στυλ και λίστες από ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να εφαρμόσετε αυτήν τη δυνατότητα στα δικά σας έγγραφα.

