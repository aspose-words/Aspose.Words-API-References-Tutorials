---
title: Αποσυνδέστε τα υποσέλιδα κεφαλίδων
linktitle: Αποσυνδέστε τα υποσέλιδα κεφαλίδων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ενώνετε και να προσαρτάτε έγγραφα του Word ενώ αποσυνδέετε κεφαλίδες και υποσέλιδα χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/unlink-headers-footers/
---

Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία χρήσης της δυνατότητας Unlink Headers Footers του Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ενώνετε και να προσαρτάτε έγγραφα του Word ενώ αποσυνδέετε τις κεφαλίδες και τα υποσέλιδα από το έγγραφο προέλευσης.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

1. Το Aspose.Words για .NET έχει εγκατασταθεί. Μπορείτε να το κατεβάσετε από τον ιστότοπο Aspose ή να το εγκαταστήσετε μέσω του NuGet.
2. Visual Studio ή οποιοδήποτε άλλο περιβάλλον ανάπτυξης C#.

## Βήμα 1: Αρχικοποιήστε τους Καταλόγους Εγγράφων

 Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο εγγράφων σας. Τροποποιήστε την τιμή του`dataDir` μεταβλητή στη διαδρομή όπου βρίσκονται τα έγγραφά σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε τα έγγραφα προέλευσης και προορισμού

 Στη συνέχεια, πρέπει να φορτώσετε τα έγγραφα προέλευσης και προορισμού χρησιμοποιώντας το Aspose.Words`Document` τάξη. Ενημερώστε τα ονόματα αρχείων στο`Document` κατασκευαστή σύμφωνα με τα ονόματα των εγγράφων σας.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Βήμα 3: Αποσυνδέστε τις κεφαλίδες και τα υποσέλιδα στο έγγραφο προέλευσης

 Για να αποσυνδέσετε τις κεφαλίδες και τα υποσέλιδα στο έγγραφο προέλευσης από τη συνέχιση των κεφαλίδων και των υποσέλιδων του εγγράφου προορισμού, πρέπει να ορίσετε`LinkToPrevious` ιδιοκτησία του`HeadersFooters` συλλογή στην πρώτη ενότητα του εγγράφου πηγής για να`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Βήμα 4: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Τώρα, μπορείτε να προσθέσετε το έγγραφο προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το`AppendDocument` μέθοδος του`Document` τάξη. ο`ImportFormatMode.KeepSourceFormatting` Η παράμετρος διασφαλίζει ότι η μορφοποίηση της πηγής διατηρείται κατά τη λειτουργία προσάρτησης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 5: Αποθηκεύστε το τελικό έγγραφο

 Τέλος, αποθηκεύστε το συγχωνευμένο έγγραφο με ενεργοποιημένη τη δυνατότητα Unlink Headers Footers χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Παράδειγμα πηγαίου κώδικα για υποσέλιδα αποσύνδεσης κεφαλίδων χρησιμοποιώντας Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δυνατότητα "Αποσύνδεση υποσέλιδων κεφαλίδων" στη C# χρησιμοποιώντας Aspose.Words για .NET:

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Αποσυνδέστε τις κεφαλίδες και τα υποσέλιδα στο έγγραφο προέλευσης για να σταματήσει αυτό
	// από τη συνέχιση των κεφαλίδων και των υποσέλιδων του εγγράφου προορισμού.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Αυτό είναι! Έχετε εφαρμόσει με επιτυχία τη δυνατότητα Unlink Headers Footers χρησιμοποιώντας το Aspose.Words για .NET. Το τελικό έγγραφο θα περιέχει το συγχωνευμένο περιεχόμενο με τις κεφαλίδες και τα υποσέλιδα από το έγγραφο προέλευσης που δεν είναι συνδεδεμένο με το έγγραφο προορισμού.