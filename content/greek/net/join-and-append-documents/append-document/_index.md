---
title: Προσάρτηση εγγράφου
linktitle: Προσάρτηση εγγράφου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσαρτάτε τα περιεχόμενα ενός εγγράφου σε ένα άλλο χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/append-document/
---

Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να προσαρτήσετε τα περιεχόμενα ενός εγγράφου σε άλλο. Ο παρεχόμενος πηγαίος κώδικας δείχνει τον τρόπο ανοίγματος των εγγράφων προέλευσης και προορισμού, εισαγωγής και προσθήκης ενοτήτων από το έγγραφο προέλευσης στο έγγραφο προορισμού.

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

## Βήμα 3: Προσθήκη ενοτήτων από το έγγραφο προέλευσης στο έγγραφο προορισμού

 Κάντε βρόχο σε όλες τις ενότητες του εγγράφου προέλευσης και εισαγάγετε κάθε ενότητα στο έγγραφο προορισμού χρησιμοποιώντας το`ImportNode` μέθοδος. Στη συνέχεια, προσθέστε την ενότητα που έχει εισαχθεί στο έγγραφο προορισμού.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Βήμα 4: Αποθηκεύστε το έγγραφο προορισμού

 Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο προορισμού χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσάρτησης ενός εγγράφου χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για Προσάρτηση εγγράφου χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Κάντε βρόχο σε όλες τις ενότητες του εγγράφου προέλευσης.
	//Οι κόμβοι ενότητας είναι άμεσα παιδιά του κόμβου Document, ώστε να μπορούμε απλώς να απαριθμήσουμε το Document.
	foreach (Section srcSection in srcDoc)
	{
		// Επειδή αντιγράφουμε μια ενότητα από το ένα έγγραφο στο άλλο,
		// απαιτείται η εισαγωγή του κόμβου Ενότητας στο έγγραφο προορισμού.
		// Αυτό προσαρμόζει τυχόν αναφορές για συγκεκριμένα έγγραφα σε στυλ, λίστες κ.λπ.
		//
		// Η εισαγωγή ενός κόμβου δημιουργεί ένα αντίγραφο του αρχικού κόμβου, αλλά το αντίγραφο
		// ss έτοιμο να εισαχθεί στο έγγραφο προορισμού.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Τώρα ο νέος κόμβος ενότητας μπορεί να προσαρτηθεί στο έγγραφο προορισμού.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```