---
title: Προσθήκη με επιλογές μορφής εισαγωγής
linktitle: Προσθήκη με επιλογές μορφής εισαγωγής
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσαρτάτε ένα έγγραφο με επιλογές μορφής εισαγωγής χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/append-with-import-format-options/
---

Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να προσαρτήσετε τα περιεχόμενα ενός εγγράφου σε ένα άλλο με επιλογές μορφής εισαγωγής. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς να ανοίξετε τα έγγραφα προέλευσης και προορισμού, να καθορίσετε επιλογές μορφής εισαγωγής και να προσαρτήσετε το έγγραφο προέλευσης στο έγγραφο προορισμού.

## Βήμα 1: Ρύθμιση του έργου

Βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET. Μπορείτε να το κατεβάσετε από[Aspose.Releases]https://releases.aspose.com/words/net/ ή χρησιμοποιήστε τη διαχείριση πακέτων NuGet για να το εγκαταστήσετε.
- Μια διαδρομή καταλόγου εγγράφων όπου βρίσκονται τα έγγραφα προέλευσης και προορισμού.

## Βήμα 2: Ανοίξτε τα έγγραφα προέλευσης και προορισμού

 Ανοίξτε τα έγγραφα προέλευσης και προορισμού χρησιμοποιώντας το`Document` κατασκευαστής τάξης. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Βήμα 3: Καθορίστε τις επιλογές μορφής εισαγωγής

 Δημιουργήστε ένα παράδειγμα του`ImportFormatOptions` κλάση για να καθορίσετε τις επιλογές μορφής εισαγωγής. Σε αυτό το παράδειγμα, χρησιμοποιούμε το`KeepSourceNumbering` ιδιότητα για να διασφαλιστεί ότι η αρίθμηση από το έγγραφο προέλευσης χρησιμοποιείται εάν υπάρχουν συγκρούσεις με το έγγραφο προορισμού.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Βήμα 4: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Χρησιμοποιήστε το`AppendDocument` μέθοδο του εγγράφου προορισμού για να προσαρτήσετε το έγγραφο προέλευσης. Πέρασμα`ImportFormatMode.UseDestinationStyles` ως δεύτερη παράμετρος για τη χρήση των στυλ και της μορφοποίησης του εγγράφου προορισμού.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Βήμα 5: Αποθηκεύστε το έγγραφο προορισμού

Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο προορισμού χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσάρτησης ενός εγγράφου με επιλογές μορφής εισαγωγής χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για Επιλογές μορφής Append With Import χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Καθορίστε ότι εάν η αρίθμηση έρχεται σε αντίθεση στα έγγραφα προέλευσης και προορισμού,
	// τότε θα χρησιμοποιηθεί αρίθμηση από το έγγραφο προέλευσης.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```