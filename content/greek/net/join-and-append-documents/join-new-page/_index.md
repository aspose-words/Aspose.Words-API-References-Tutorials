---
title: Εγγραφείτε στη Νέα Σελίδα
linktitle: Εγγραφείτε στη Νέα Σελίδα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ενώνετε δύο έγγραφα σε μια νέα σελίδα διατηρώντας παράλληλα τη μορφοποίηση χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/join-new-page/
---

Αυτό το σεμινάριο εξηγεί πώς να συνδέσετε δύο έγγραφα σε μια νέα σελίδα χρησιμοποιώντας το Aspose.Words για .NET. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς να προσαρτήσετε ένα έγγραφο στο τέλος ενός άλλου εγγράφου ενώ ξεκινάτε το επισυναπτόμενο έγγραφο σε μια νέα σελίδα.

## Βήμα 1: Ρύθμιση του έργου

Βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET. Μπορείτε να το κατεβάσετε από[Aspose.Releases]https://releases.aspose.com/words/net/ ή χρησιμοποιήστε τη διαχείριση πακέτων NuGet για να το εγκαταστήσετε.
- Μια διαδρομή καταλόγου εγγράφων όπου βρίσκονται τα έγγραφα προέλευσης και προορισμού.

## Βήμα 2: Ανοίξτε τα έγγραφα προέλευσης και προορισμού

 Ανοίξτε τα έγγραφα προέλευσης και προορισμού χρησιμοποιώντας το`Document` κατασκευαστής τάξης. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Βήμα 3: Ρύθμιση έναρξης ενότητας νέας σελίδας

 Για να ξεκινήσετε το επισυναπτόμενο έγγραφο σε μια νέα σελίδα, ορίστε το`SectionStart` ιδιότητα της πρώτης ενότητας στο έγγραφο προέλευσης to`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Βήμα 4: Προσθέστε το έγγραφο προέλευσης

 Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το`AppendDocument` μέθοδος του`Document` τάξη. Ρυθμίστε τη λειτουργία μορφής εισαγωγής σε`ImportFormatMode.KeepSourceFormatting` για να διατηρήσετε τα πρωτότυπα στυλ από το έγγραφο προέλευσης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 5: Αποθηκεύστε το τροποποιημένο έγγραφο

 Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο προορισμού χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Αυτό ολοκληρώνει την υλοποίηση της ένωσης δύο εγγράφων σε μια νέα σελίδα χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για Join New Page χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Ρυθμίστε το συνημμένο έγγραφο ώστε να ξεκινά από μια νέα σελίδα.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Προσθέστε το έγγραφο προέλευσης χρησιμοποιώντας τα πρωτότυπα στυλ που βρίσκονται στο έγγραφο προέλευσης.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```