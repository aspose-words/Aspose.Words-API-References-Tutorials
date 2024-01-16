---
title: Διατηρήστε την πηγή μαζί
linktitle: Διατηρήστε την πηγή μαζί
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.Words για .NET για τη σύνδεση και την προσθήκη εγγράφων του Word, ενώ διατηρείτε το περιεχόμενο προέλευσης μαζί με το έγγραφο προορισμού.
type: docs
weight: 10
url: /el/net/join-and-append-documents/keep-source-together/
---

Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία χρήσης της δυνατότητας Keep Source Together του Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ενώνετε και να προσαρτάτε πολλά έγγραφα του Word, ενώ διατηρείτε το περιεχόμενο του εγγράφου προέλευσης μαζί με το περιεχόμενο του εγγράφου προορισμού. 

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

## Βήμα 3: Ορίστε το έγγραφο προέλευσης ώστε να εμφανίζεται μετά το περιεχόμενο του εγγράφου προορισμού

 Για να διασφαλίσετε ότι το έγγραφο προέλευσης εμφανίζεται αμέσως μετά το περιεχόμενο του εγγράφου προορισμού, πρέπει να ορίσετε το`SectionStart` ιδιότητα της πρώτης ενότητας στο έγγραφο προέλευσης to`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Βήμα 4: Ορίστε τη μορφοποίηση παραγράφου "Keep with Next" για το έγγραφο προέλευσης

Για να διατηρήσετε τις παραγράφους στο έγγραφο προέλευσης μαζί, μπορείτε να επαναλάβετε κάθε παράγραφο στο έγγραφο και να ορίσετε το`KeepWithNext`ιδιοκτησία σε`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Βήμα 5: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Τώρα, μπορείτε να προσθέσετε το έγγραφο προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το`AppendDocument` μέθοδος του`Document` τάξη. ο`ImportFormatMode.KeepSourceFormatting` Η παράμετρος διασφαλίζει ότι η μορφοποίηση της πηγής διατηρείται κατά τη λειτουργία προσάρτησης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 6: Αποθηκεύστε το τελικό έγγραφο

 Τέλος, αποθηκεύστε το συγχωνευμένο έγγραφο με ενεργοποιημένη τη δυνατότητα "Keep Source Together" χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Παράδειγμα πηγαίου κώδικα για το Keep Source Together χρησιμοποιώντας το Aspose.Words για .NET 

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δυνατότητα "Keep Source Together" στη C# χρησιμοποιώντας το Aspose.Words για .NET:


```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Ρυθμίστε το έγγραφο προέλευσης ώστε να εμφανίζεται αμέσως μετά το περιεχόμενο του εγγράφου προορισμού.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Αυτό είναι! Έχετε εφαρμόσει με επιτυχία τη δυνατότητα Keep Source Together χρησιμοποιώντας το Aspose.Words για .NET. Το τελικό έγγραφο θα περιέχει το συγχωνευμένο περιεχόμενο με τις παραγράφους στο έγγραφο προέλευσης που θα τηρούνται μαζί.