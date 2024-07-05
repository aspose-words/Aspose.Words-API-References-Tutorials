---
title: Μορφοποίηση πηγής διατήρησης λίστας
linktitle: Μορφοποίηση πηγής διατήρησης λίστας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να διατηρείτε τη μορφοποίηση λίστας ενώ συνδέετε και προσαρτάτε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/list-keep-source-formatting/
---

Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία χρήσης της δυνατότητας Μορφοποίησης πηγής λίστας διατήρησης του Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ενώνετε και να προσαρτάτε έγγραφα του Word, διατηρώντας παράλληλα τη μορφοποίηση πηγής των λιστών.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Βήμα 3: Ρυθμίστε το έγγραφο προέλευσης σε συνεχή ροή

 Για να διασφαλίσετε ότι το περιεχόμενο από το έγγραφο προέλευσης ρέει συνεχώς όταν προσαρτάται στο έγγραφο προορισμού, πρέπει να ορίσετε`SectionStart` ιδιότητα της πρώτης ενότητας στο έγγραφο προέλευσης to`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Βήμα 4: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Τώρα, μπορείτε να προσθέσετε το έγγραφο προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το`AppendDocument` μέθοδος του`Document` τάξη. ο`ImportFormatMode.KeepSourceFormatting`Η παράμετρος διασφαλίζει ότι η μορφοποίηση της πηγής, συμπεριλαμβανομένης της μορφοποίησης των λιστών, διατηρείται κατά τη λειτουργία προσάρτησης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 5: Αποθηκεύστε το τελικό έγγραφο

 Τέλος, αποθηκεύστε το συγχωνευμένο έγγραφο με ενεργοποιημένη τη δυνατότητα Μορφοποίησης πηγής λίστας διατήρησης χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Παράδειγμα πηγαίου κώδικα για τη μορφοποίηση πηγών λίστας διατήρησης χρησιμοποιώντας το Aspose.Words για .NET 

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δυνατότητα List Keep Source Formatting σε C# χρησιμοποιώντας Aspose.Words για .NET:

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Προσθέστε το περιεχόμενο του εγγράφου ώστε να ρέει συνεχώς.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Αυτό είναι! Υλοποιήσατε με επιτυχία τη δυνατότητα μορφοποίησης πηγών λίστας διατήρησης χρησιμοποιώντας το Aspose.Words για .NET. Το τελικό έγγραφο θα περιέχει το συγχωνευμένο περιεχόμενο με τη μορφοποίηση της λίστας του εγγράφου προέλευσης να διατηρείται.