---
title: Σύνδεση υποσέλιδων κεφαλίδων
linktitle: Σύνδεση υποσέλιδων κεφαλίδων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να συνδέετε κεφαλίδες και υποσέλιδα ενώ συνδέετε και προσαρτάτε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/link-headers-footers/
---

Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία χρήσης της δυνατότητας Link Headers Footers του Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ενώνετε και να προσαρτάτε πολλά έγγραφα του Word ενώ συνδέετε τις κεφαλίδες και τα υποσέλιδα του εγγράφου προέλευσης με την προηγούμενη ενότητα του εγγράφου προορισμού.

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

## Βήμα 3: Ρυθμίστε το προσαρτημένο έγγραφο ώστε να εμφανίζεται σε νέα σελίδα

 Για να βεβαιωθείτε ότι το περιεχόμενο από το έγγραφο προέλευσης εμφανίζεται σε μια νέα σελίδα στο έγγραφο προορισμού, πρέπει να ορίσετε το`SectionStart` ιδιότητα της πρώτης ενότητας στο έγγραφο προέλευσης to`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Βήμα 4: Συνδέστε τις κεφαλίδες και τα υποσέλιδα με την προηγούμενη ενότητα

Για να συνδέσετε τις κεφαλίδες και τα υποσέλιδα του εγγράφου προέλευσης με την προηγούμενη ενότητα του εγγράφου προορισμού, μπορείτε να χρησιμοποιήσετε το`LinkToPrevious` μέθοδος του`HeadersFooters` συλλογή. Περνώντας`true` Ως παράμετρος, παρακάμπτετε τυχόν υπάρχουσες κεφαλίδες ή υποσέλιδα στο έγγραφο προέλευσης.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Βήμα 5: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Τώρα, μπορείτε να προσθέσετε το έγγραφο προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το`AppendDocument` μέθοδος του`Document` τάξη. ο`ImportFormatMode.KeepSourceFormatting` Η παράμετρος διασφαλίζει ότι η μορφοποίηση της πηγής διατηρείται κατά τη λειτουργία προσάρτησης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 6: Αποθηκεύστε το τελικό έγγραφο

 Τέλος, αποθηκεύστε το συγχωνευμένο έγγραφο με τις συνδεδεμένες κεφαλίδες και υποσέλιδα χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Παράδειγμα πηγαίου κώδικα για υποσέλιδα κεφαλίδων συνδέσμων που χρησιμοποιούν Aspose.Words για .NET 

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δυνατότητα "Σύνδεσμοι υποσέλιδων κεφαλίδων" σε C# χρησιμοποιώντας Aspose.Words για .NET:


```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ρυθμίστε το συνημμένο έγγραφο ώστε να εμφανίζεται σε νέα σελίδα.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Συνδέστε τις κεφαλίδες και τα υποσέλιδα στο έγγραφο προέλευσης με την προηγούμενη ενότητα.
	// Αυτό θα αντικαταστήσει τυχόν κεφαλίδες ή υποσέλιδα που έχουν ήδη βρεθεί στο έγγραφο προέλευσης.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Αυτό είναι! Έχετε εφαρμόσει με επιτυχία τη δυνατότητα Link Headers Footers χρησιμοποιώντας το Aspose.Words για .NET. Το τελικό έγγραφο θα περιέχει το συγχωνευμένο περιεχόμενο με τις κεφαλίδες και τα υποσέλιδα από το έγγραφο προέλευσης που συνδέεται με την προηγούμενη ενότητα του εγγράφου προορισμού.