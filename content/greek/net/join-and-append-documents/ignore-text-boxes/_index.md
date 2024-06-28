---
title: Αγνοήστε τα πλαίσια κειμένου
linktitle: Αγνοήστε τα πλαίσια κειμένου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσαρτάτε ένα έγγραφο ενώ αγνοείτε τη μορφοποίηση πλαισίου κειμένου χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/ignore-text-boxes/
---

Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να προσαρτήσετε ένα έγγραφο διατηρώντας παράλληλα τη μορφοποίηση των πλαισίων κειμένου. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς να ρυθμίσετε τις επιλογές μορφής εισαγωγής για να συμπεριλάβετε πλαίσια κειμένου κατά τη διαδικασία προσάρτησης.

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

## Βήμα 3: Ρυθμίστε τις επιλογές μορφής εισαγωγής

 Δημιουργήστε ένα παράδειγμα του`ImportFormatOptions` τάξη και ορίστε το`IgnoreTextBoxes`ιδιοκτησία σε`false`. Αυτό διασφαλίζει ότι τα πλαίσια κειμένου περιλαμβάνονται κατά τη διαδικασία προσάρτησης, διατηρώντας παράλληλα τη μορφοποίησή τους.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Βήμα 4: Προσθήκη περιεχομένου πλαισίου κειμένου

 Δημιουργώ ένα`NodeImporter`αντικείμενο και χρησιμοποιήστε το για να εισαγάγετε κόμβους πλαισίου κειμένου από το έγγραφο προέλευσης στο έγγραφο προορισμού. Επαναλάβετε κάθε παράγραφο στο έγγραφο προέλευσης και εισαγάγετε το στο έγγραφο προορισμού.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Βήμα 5: Αποθηκεύστε το έγγραφο προορισμού

Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο προορισμού χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσάρτησης ενός εγγράφου διατηρώντας παράλληλα τη μορφοποίηση πλαισίου κειμένου χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για Ignore Text Boxes χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Διατηρήστε τη μορφοποίηση των πλαισίων κειμένου προέλευσης κατά την εισαγωγή.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```