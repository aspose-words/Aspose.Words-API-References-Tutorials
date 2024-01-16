---
title: Διατήρηση αρίθμησης πηγών
linktitle: Διατήρηση αρίθμησης πηγών
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσαρτάτε ένα έγγραφο διατηρώντας παράλληλα τη μορφοποίηση αρίθμησης πηγής στο Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/keep-source-numbering/
---

Αυτό το σεμινάριο εξηγεί πώς να προσαρτήσετε ένα έγγραφο προέλευσης σε ένα έγγραφο προορισμού διατηρώντας παράλληλα την αρχική μορφοποίηση αρίθμησης αριθμημένων παραγράφων χρησιμοποιώντας το Aspose.Words για .NET.

## Βήμα 1: Ρύθμιση του έργου

Βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET. Μπορείτε να το κατεβάσετε από[Aspose.Releases]https://releases.aspose.com/words/net/ ή χρησιμοποιήστε τη διαχείριση πακέτων NuGet για να το εγκαταστήσετε.
- Μια διαδρομή καταλόγου εγγράφων όπου θα αποθηκευτούν τα έγγραφα προέλευσης και προορισμού.

## Βήμα 2: Δημιουργήστε τα έγγραφα προορισμού και προέλευσης

 Δημιουργία περιπτώσεων`Document` για τα έγγραφα προορισμού και προέλευσης.

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Βήμα 3: Διατηρήστε την αρίθμηση της πηγής κατά την εισαγωγή

 Για να διατηρήσετε τη μορφοποίηση αρίθμησης των αριθμημένων παραγράφων από το έγγραφο προέλευσης, δημιουργήστε μια παρουσία του`ImportFormatOptions` και να θέσει`KeepSourceNumbering` προς την`true` . Χρησιμοποίησε ένα`NodeImporter` για εισαγωγή κόμβων από το έγγραφο προέλευσης στο έγγραφο προορισμού, καθορίζοντας`ImportFormatMode.KeepSourceFormatting` και το`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Βήμα 4: Εισαγωγή και προσθήκη παραγράφων

Επαναλάβετε τις παραγράφους στο έγγραφο προέλευσης και εισαγάγετε κάθε παράγραφο στο έγγραφο προορισμού χρησιμοποιώντας το`importer`. Προσθέστε τους εισαγόμενους κόμβους στο σώμα του εγγράφου προορισμού.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Βήμα 5: Αποθηκεύστε το τροποποιημένο έγγραφο

 Αποθηκεύστε το τροποποιημένο έγγραφο χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσθήκης ενός εγγράφου προέλευσης σε ένα έγγραφο προορισμού, διατηρώντας παράλληλα την αρχική μορφοποίηση αρίθμησης χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για τη διατήρηση αρίθμησης πηγών χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Διατηρήστε τη μορφοποίηση της λίστας πηγών κατά την εισαγωγή αριθμημένων παραγράφων.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```