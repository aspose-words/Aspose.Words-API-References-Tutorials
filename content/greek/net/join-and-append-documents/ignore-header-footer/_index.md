---
title: Παράβλεψη υποσέλιδου κεφαλίδας
linktitle: Παράβλεψη υποσέλιδου κεφαλίδας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσαρτάτε ένα έγγραφο ενώ αγνοείτε το περιεχόμενο κεφαλίδας και υποσέλιδου χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/ignore-header-footer/
---

Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να προσαρτήσετε ένα έγγραφο ενώ αγνοείτε το περιεχόμενο της κεφαλίδας και του υποσέλιδου. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς να ρυθμίσετε τις επιλογές μορφής εισαγωγής για να εξαιρέσετε την κεφαλίδα και το υποσέλιδο κατά τη διαδικασία προσάρτησης.

## Βήμα 1: Ρύθμιση του έργου

Βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET. Μπορείτε να το κατεβάσετε από[Aspose.Releases]https://releases.aspose.com/words/net/ ή χρησιμοποιήστε τη διαχείριση πακέτων NuGet για να το εγκαταστήσετε.
- Μια διαδρομή καταλόγου εγγράφων όπου βρίσκονται τα έγγραφα προέλευσης και προορισμού.

## Βήμα 2: Ανοίξτε τα έγγραφα προέλευσης και προορισμού

 Ανοίξτε τα έγγραφα προέλευσης και προορισμού χρησιμοποιώντας το`Document` κατασκευαστής τάξης. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Βήμα 3: Ρυθμίστε τις επιλογές μορφής εισαγωγής

 Δημιουργήστε ένα παράδειγμα του`ImportFormatOptions` τάξη και ορίστε το`IgnoreHeaderFooter`ιδιοκτησία σε`false`. Αυτό διασφαλίζει ότι το περιεχόμενο της κεφαλίδας και του υποσέλιδου συμπεριλαμβάνεται κατά τη διαδικασία προσάρτησης.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Βήμα 4: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Χρησιμοποιήστε το`AppendDocument` μέθοδο του εγγράφου προορισμού για να προσαρτήσετε το έγγραφο προέλευσης. Πέρασμα`ImportFormatMode.KeepSourceFormatting`ως δεύτερη παράμετρος και οι επιλογές μορφής εισαγωγής ως τρίτη παράμετρος.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Βήμα 5: Αποθηκεύστε το έγγραφο προορισμού

Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο προορισμού χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσάρτησης ενός εγγράφου, ενώ αγνοεί το περιεχόμενο της κεφαλίδας και του υποσέλιδου χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για το Υποσέλιδο Ignore Header χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```