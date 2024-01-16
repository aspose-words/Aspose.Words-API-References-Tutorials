---
title: Διατήρηση μορφοποίησης πηγής
linktitle: Διατήρηση μορφοποίησης πηγής
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσαρτάτε ένα έγγραφο προέλευσης σε ένα έγγραφο προορισμού διατηρώντας παράλληλα την αρχική μορφοποίηση χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/keep-source-formatting/
---

Αυτό το σεμινάριο δείχνει πώς να προσαρτήσετε ένα έγγραφο προέλευσης σε ένα έγγραφο προορισμού διατηρώντας παράλληλα την αρχική μορφοποίηση του εγγράφου προέλευσης χρησιμοποιώντας το Aspose.Words για .NET.

## Βήμα 1: Ρύθμιση του έργου

Βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET. Μπορείτε να το κατεβάσετε από[Aspose.Releases]https://releases.aspose.com/words/net/ ή χρησιμοποιήστε τη διαχείριση πακέτων NuGet για να το εγκαταστήσετε.
- Μια διαδρομή καταλόγου εγγράφων όπου θα αποθηκευτούν τα έγγραφα προέλευσης και προορισμού.

## Βήμα 2: Δημιουργήστε τα έγγραφα προορισμού και προέλευσης

 Δημιουργία περιπτώσεων`Document` για τα έγγραφα προορισμού και προέλευσης.

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Βήμα 3: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Χρησιμοποιήστε το`AppendDocument` μέθοδο του εγγράφου προορισμού για να προσαρτήσετε το έγγραφο προέλευσης. Πέρασμα`ImportFormatMode.KeepSourceFormatting` ως λειτουργία μορφής εισαγωγής για να διατηρήσετε την αρχική μορφοποίηση του εγγράφου προέλευσης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 4: Αποθηκεύστε το τροποποιημένο έγγραφο

 Αποθηκεύστε το τροποποιημένο έγγραφο χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσθήκης ενός εγγράφου προέλευσης σε ένα έγγραφο προορισμού διατηρώντας παράλληλα την αρχική μορφοποίηση χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για τη μορφοποίηση Keep Source χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού.
	// Περάστε τη λειτουργία μορφής για να διατηρήσετε την αρχική μορφοποίηση του εγγράφου προέλευσης κατά την εισαγωγή του.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```