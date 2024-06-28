---
title: Καταργήστε τα υποσέλιδα κεφαλίδων πηγής
linktitle: Καταργήστε τα υποσέλιδα κεφαλίδων πηγής
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να αφαιρείτε κεφαλίδες και υποσέλιδα ενώ συνδέετε και προσαρτάτε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/remove-source-headers-footers/
---

Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία χρήσης της δυνατότητας Remove Source Headers Footers του Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ενώνετε και να προσαρτάτε έγγραφα του Word ενώ αφαιρείτε κεφαλίδες και υποσέλιδα από το έγγραφο προέλευσης.

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

Στη συνέχεια, πρέπει να φορτώσετε τα έγγραφα προέλευσης και προορισμού χρησιμοποιώντας το Aspose.Words.`Document` τάξη. Ενημερώστε τα ονόματα αρχείων στο`Document` κατασκευαστή σύμφωνα με τα ονόματα των εγγράφων σας.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Βήμα 3: Καταργήστε τις κεφαλίδες και τα υποσέλιδα από τις ενότητες του εγγράφου προέλευσης

 Για να αφαιρέσετε τις κεφαλίδες και τα υποσέλιδα από κάθε ενότητα στο έγγραφο προέλευσης, μπορείτε να επαναλάβετε τις ενότητες χρησιμοποιώντας α`foreach` βρόχο και καλέστε το`ClearHeadersFooters` μέθοδος.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Βήμα 4: Απενεργοποιήστε τη ρύθμιση "LinkToPrevious" για τα HeadersFooters

Ακόμη και μετά την εκκαθάριση των κεφαλίδων και των υποσέλιδων από το έγγραφο προέλευσης, υπάρχει πιθανότητα η ρύθμιση "LinkToPrevious" για`HeadersFooters` μπορεί ακόμα να ρυθμιστεί. Για να αποφύγετε αυτήν τη συμπεριφορά, πρέπει να τη ρυθμίσετε ρητά σε`false` για την πρώτη ενότητα`HeadersFooters` ιδιοκτησία.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Βήμα 5: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Τώρα, μπορείτε να προσθέσετε το έγγραφο προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το`AppendDocument` μέθοδος του`Document` τάξη. ο`ImportFormatMode.KeepSourceFormatting` Η παράμετρος διασφαλίζει ότι η μορφοποίηση της πηγής διατηρείται κατά τη λειτουργία προσάρτησης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 6: Αποθηκεύστε το τελικό έγγραφο

 Τέλος, αποθηκεύστε το συγχωνευμένο έγγραφο με τη δυνατότητα Κατάργηση υποσέλιδων κεφαλίδων προέλευσης ενεργοποιημένη χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Παράδειγμα πηγαίου κώδικα για τα υποσέλιδα Remove Source Headers χρησιμοποιώντας Aspose.Words για .NET 

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δυνατότητα "Κατάργηση υποσέλιδων κεφαλίδων προέλευσης" στη C# χρησιμοποιώντας το Aspose.Words για .NET:


```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Καταργήστε τις κεφαλίδες και τα υποσέλιδα από καθεμία από τις ενότητες του εγγράφου προέλευσης.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Ακόμη και μετά τη διαγραφή των κεφαλίδων και των υποσέλιδων από το έγγραφο προέλευσης, η ρύθμιση "LinkToPrevious".
	// για HeadersFooters μπορούν ακόμα να οριστούν. Αυτό θα κάνει τις κεφαλίδες και τα υποσέλιδα να συνεχίσουν από τον προορισμό
	// έγγραφο. Αυτό θα πρέπει να οριστεί σε false για να αποφευχθεί αυτή η συμπεριφορά.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Αυτό είναι! Έχετε εφαρμόσει με επιτυχία τη δυνατότητα Κατάργηση υποσέλιδων κεφαλίδων προέλευσης χρησιμοποιώντας το Aspose.Words για .NET. Το τελικό έγγραφο θα περιέχει το συγχωνευμένο περιεχόμενο με τις κεφαλίδες και τα υποσέλιδα που έχουν αφαιρεθεί από το έγγραφο προέλευσης.