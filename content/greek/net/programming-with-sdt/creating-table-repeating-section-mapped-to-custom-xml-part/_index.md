---
title: Δημιουργία πίνακα Επαναλαμβανόμενη ενότητα αντιστοιχισμένη σε προσαρμοσμένο τμήμα Xml
linktitle: Δημιουργία πίνακα Επαναλαμβανόμενη ενότητα αντιστοιχισμένη σε προσαρμοσμένο τμήμα Xml
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε έναν πίνακα με μια επαναλαμβανόμενη ενότητα αντιστοιχισμένη σε ένα CustomXmlPart σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Αυτό το σεμινάριο δείχνει πώς να δημιουργήσετε έναν πίνακα με μια επαναλαμβανόμενη ενότητα αντιστοιχισμένη σε ένα προσαρμοσμένο τμήμα Xml σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Η ενότητα επανάληψης σάς επιτρέπει να προσθέτετε δυναμικά σειρές με βάση τα δεδομένα XML που είναι αποθηκευμένα στο προσαρμοσμένο τμήμα Xml.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"`με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα Document and DocumentBuilder
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`DocumentBuilder` για τη δημιουργία του περιεχομένου του εγγράφου.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Προσθέστε προσαρμοσμένα δεδομένα XML σε ένα CustomXmlPart
 Δημιουργώ ένα`CustomXmlPart` και προσθέστε προσαρμοσμένα δεδομένα XML σε αυτό. Σε αυτό το παράδειγμα, δημιουργούμε μια συμβολοσειρά XML που αντιπροσωπεύει μια συλλογή βιβλίων με τους τίτλους και τους συγγραφείς τους.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Βήμα 4: Δημιουργήστε μια δομή πίνακα και πίνακα
 Ξεκινήστε τη δημιουργία ενός πίνακα χρησιμοποιώντας το`StartTable` μέθοδος του`DocumentBuilder` . Προσθέστε κελιά πίνακα και περιεχόμενο χρησιμοποιώντας το`InsertCell`και`Write` μεθόδους.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Βήμα 5: Δημιουργήστε την ενότητα Επαναλαμβανόμενης Αντιστοίχισης σε Προσαρμοσμένη XML
 Δημιουργώ ένα`StructuredDocumentTag` με`SdtType.RepeatingSection` για να αναπαραστήσετε το επαναλαμβανόμενο τμήμα. Ορίστε την αντιστοίχιση XML για την επαναλαμβανόμενη ενότητα χρησιμοποιώντας το`SetMapping` μέθοδος του`XmlMapping` ιδιοκτησία. Σε αυτό το παράδειγμα, αντιστοιχίζουμε την ενότητα που επαναλαμβάνεται`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Βήμα 6: Δημιουργήστε το στοιχείο Επαναλαμβανόμενης Ενότητας και προσθέστε κελιά
 Δημιουργώ ένα`StructuredDocumentTag` με`SdtType.RepeatingSectionItem` για να αναπαραστήσετε το επαναλαμβανόμενο στοιχείο ενότητας. Προσθέστε το ως παιδί στην ενότητα επανάληψης.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Δημιουργώ ένα`Row` για να αναπαραστήσετε κάθε στοιχείο στην επαναλαμβανόμενη ενότητα και να το προσθέσετε στο στοιχείο επαναλαμβανόμενης ενότητας.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Βήμα 7: Προσθέστε στοιχεία ελέγχου περιεχομένου στην ενότητα Επανάληψη
 Δημιουργώ`StructuredDocumentTag` αντικείμενα με`SdtType.PlainText`

  για να αντιπροσωπεύουν τα στοιχεία ελέγχου περιεχομένου τίτλου και συγγραφέα. Ορίστε την αντιστοίχιση XML για κάθε στοιχείο ελέγχου περιεχομένου χρησιμοποιώντας το`SetMapping` μέθοδος του`XmlMapping` ιδιοκτησία. Σε αυτό το παράδειγμα, αντιστοιχίζουμε το στοιχείο ελέγχου τίτλου σε`/books[1]/book[1]/title[1]` και τον έλεγχο του συγγραφέα να`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Βήμα 8: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το τροποποιημένο έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Παράδειγμα πηγαίου κώδικα για τη δημιουργία πίνακα επαναλαμβανόμενης ενότητας αντιστοιχισμένη σε προσαρμοσμένο τμήμα Xml χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Αυτό είναι! Έχετε δημιουργήσει επιτυχώς έναν πίνακα με μια επαναλαμβανόμενη ενότητα αντιστοιχισμένη σε ένα CustomXmlPart στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.