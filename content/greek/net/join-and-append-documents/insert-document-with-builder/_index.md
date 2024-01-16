---
title: Εισαγωγή εγγράφου με το Builder
linktitle: Εισαγωγή εγγράφου με το Builder
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισάγετε ένα έγγραφο στο τέλος ενός άλλου εγγράφου χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/insert-document-with-builder/
---

 Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να εισαγάγετε ένα έγγραφο σε άλλο έγγραφο χρησιμοποιώντας το`DocumentBuilder` τάξη. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς να εισαγάγετε ένα έγγραφο στο τέλος ενός άλλου εγγράφου διατηρώντας παράλληλα τη μορφοποίηση προέλευσης.

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

## Βήμα 3: Αρχικοποιήστε το DocumentBuilder

 Δημιουργήστε μια νέα παρουσία του`DocumentBuilder` κλάση και περάστε το έγγραφο προορισμού ως παράμετρο.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Βήμα 4: Τοποθετήστε το DocumentBuilder

 Μετακίνησε το`DocumentBuilder` στο τέλος του εγγράφου χρησιμοποιώντας το`MoveToDocumentEnd` μέθοδος. Εισαγάγετε μια αλλαγή σελίδας για να διαχωρίσετε το υπάρχον περιεχόμενο από το εισαγόμενο έγγραφο.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Βήμα 5: Εισαγάγετε το έγγραφο προέλευσης

 Χρησιμοποιήστε το`InsertDocument` μέθοδος του`DocumentBuilder` κλάση για να εισαγάγετε το έγγραφο προέλευσης στο έγγραφο προορισμού. Ρυθμίστε τη λειτουργία μορφής εισαγωγής σε`ImportFormatMode.KeepSourceFormatting` για να διατηρήσετε τη μορφοποίηση της πηγής.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 6: Αποθηκεύστε το τροποποιημένο έγγραφο

 Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο προορισμού χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Αυτό ολοκληρώνει την υλοποίηση της εισαγωγής ενός εγγράφου σε άλλο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για το Insert Document With Builder με χρήση Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```