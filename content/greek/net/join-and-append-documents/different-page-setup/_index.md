---
title: Διαφορετική ρύθμιση σελίδας
linktitle: Διαφορετική ρύθμιση σελίδας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσαρτάτε ένα έγγραφο με διαφορετικές ρυθμίσεις ρύθμισης σελίδας χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/different-page-setup/
---

Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να προσαρτήσετε ένα έγγραφο με διαφορετικές ρυθμίσεις ρύθμισης σελίδας σε άλλο έγγραφο. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς να ρυθμίσετε διαφορετικές ρυθμίσεις σελίδας για τα έγγραφα προέλευσης και προορισμού και να εξασφαλίσετε τη σωστή συνέχιση και αρίθμηση.

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

## Βήμα 3: Ρυθμίστε τις ρυθμίσεις σελίδας για το έγγραφο προέλευσης

 Προσαρμόστε τις ρυθμίσεις ρύθμισης σελίδας του εγγράφου προέλευσης για να διασφαλίσετε τη σωστή συνέχιση και αρίθμηση. Σε αυτό το παράδειγμα, ορίσαμε την ενότητα start σε`SectionStart.Continuous`και επανεκκινήστε την αρίθμηση σελίδων. Βεβαιωνόμαστε επίσης ότι το πλάτος, το ύψος και ο προσανατολισμός της σελίδας ταιριάζουν με το τελευταίο τμήμα του εγγράφου προορισμού.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Βήμα 4: Τροποποίηση της μορφοποίησης παραγράφου

 Για να διατηρήσετε τη σωστή μορφοποίηση, επαναλάβετε όλες τις παραγράφους στο έγγραφο προέλευσης και ορίστε το`KeepWithNext`ιδιοκτησία σε`true`. Αυτό διασφαλίζει ότι οι παράγραφοι παραμένουν μαζί κατά τη διαδικασία προσάρτησης.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Βήμα 5: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Χρησιμοποιήστε το`AppendDocument` μέθοδος του εγγράφου προορισμού για την προσθήκη του τροποποιημένου εγγράφου προέλευσης στο έγγραφο προορισμού, διατηρώντας τη μορφοποίηση προέλευσης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Βήμα 6: Αποθηκεύστε το έγγραφο προορισμού

Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο προορισμού χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσάρτησης ενός εγγράφου με διαφορετικές ρυθμίσεις ρύθμισης σελίδας χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για Διαφορετική ρύθμιση σελίδας χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ρυθμίστε το έγγραφο προέλευσης ώστε να συνεχίζει αμέσως μετά το τέλος του εγγράφου προορισμού.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Επανεκκινήστε την αρίθμηση σελίδων στην αρχή του εγγράφου προέλευσης.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//Για να διασφαλίσετε ότι αυτό δεν συμβαίνει όταν το έγγραφο προέλευσης έχει διαφορετικές ρυθμίσεις ρύθμισης σελίδας, βεβαιωθείτε ότι το
	// Οι ρυθμίσεις είναι πανομοιότυπες μεταξύ της τελευταίας ενότητας του εγγράφου προορισμού.
	// Εάν υπάρχουν περαιτέρω συνεχείς ενότητες που ακολουθούν στο έγγραφο προέλευσης,
	// αυτό θα πρέπει να επαναληφθεί για αυτές τις ενότητες.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Επαναλάβετε όλες τις ενότητες στο έγγραφο προέλευσης.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```