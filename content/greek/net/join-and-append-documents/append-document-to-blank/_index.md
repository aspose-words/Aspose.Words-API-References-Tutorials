---
title: Προσθήκη εγγράφου σε κενό
linktitle: Προσθήκη εγγράφου σε κενό
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να προσαρτήσετε ένα έγγραφο σε ένα κενό έγγραφο προορισμού στο Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/append-document-to-blank/
---

Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να προσαρτήσετε τα περιεχόμενα ενός εγγράφου σε ένα κενό έγγραφο προορισμού. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς να δημιουργήσετε ένα νέο έγγραφο, να αφαιρέσετε το περιεχόμενό του και, στη συνέχεια, να προσαρτήσετε το έγγραφο προέλευσης σε αυτό.

## Βήμα 1: Ρύθμιση του έργου

Βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET. Μπορείτε να το κατεβάσετε από[Aspose.Releases]https://releases.aspose.com/words/net/ ή χρησιμοποιήστε τη διαχείριση πακέτων NuGet για να το εγκαταστήσετε.
- Μια διαδρομή καταλόγου εγγράφων όπου βρίσκονται τα έγγραφα προέλευσης και προορισμού.

## Βήμα 2: Δημιουργήστε ένα νέο έγγραφο προορισμού

 Δημιούργησε ένα νέο`Document` αντικείμενο για το έγγραφο προορισμού.

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Βήμα 3: Καταργήστε το υπάρχον περιεχόμενο από το έγγραφο προορισμού

 Για να διασφαλίσετε ένα καθαρό έγγραφο προορισμού, αφαιρέστε όλο το υπάρχον περιεχόμενο από το έγγραφο χρησιμοποιώντας το`RemoveAllChildren` μέθοδος.

```csharp
dstDoc.RemoveAllChildren();
```

## Βήμα 4: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Προσθέστε τα περιεχόμενα του εγγράφου προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το`AppendDocument` μέθοδος με`ImportFormatMode.KeepSourceFormatting` επιλογή.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 5: Αποθηκεύστε το έγγραφο προορισμού

 Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο προορισμού χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσάρτησης ενός εγγράφου σε ένα κενό έγγραφο προορισμού χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για Προσάρτηση εγγράφου σε κενό χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Το έγγραφο προορισμού δεν είναι κενό, με αποτέλεσμα συχνά να εμφανίζεται μια κενή σελίδα πριν από το επισυναπτόμενο έγγραφο.
	// Αυτό οφείλεται στο ότι το βασικό έγγραφο έχει μια κενή ενότητα και το νέο έγγραφο ξεκινά στην επόμενη σελίδα.
	// Καταργήστε όλο το περιεχόμενο από το έγγραφο προορισμού πριν το προσαρτήσετε.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```