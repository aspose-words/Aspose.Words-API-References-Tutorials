---
title: Εύρος ετικετών δομημένου εγγράφου Έναρξη αντιστοίχισης Xml
linktitle: Εύρος ετικετών δομημένου εγγράφου Έναρξη αντιστοίχισης Xml
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ρυθμίζετε την αντιστοίχιση XML για ένα εύρος ετικετών δομημένου εγγράφου που ξεκινά σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Αυτό το σεμινάριο εξηγεί πώς να ρυθμίσετε την αντιστοίχιση XML για μια αρχή εύρους ετικετών δομημένου εγγράφου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Η αντιστοίχιση XML σάς επιτρέπει να εμφανίζετε συγκεκριμένα τμήματα μιας πηγής δεδομένων XML μέσα στο στοιχείο ελέγχου περιεχομένου.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφό σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο και δημιουργήστε τμήμα XML
 Φορτώστε το έγγραφο του Word χρησιμοποιώντας το`Document` κατασκευαστή, περνώντας τη διαδρομή προς το έγγραφο ως παράμετρο. Δημιουργήστε ένα τμήμα XML που περιέχει τα δεδομένα που θέλετε να εμφανίσετε στην ετικέτα δομημένου εγγράφου.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Βήμα 3: Ορισμός αντιστοίχισης XML για ετικέτα δομημένου εγγράφου
Ανακτήστε το εύρος ετικετών δομημένου εγγράφου που ξεκινά από το έγγραφο. Στη συνέχεια, ορίστε την αντιστοίχιση XML για την ετικέτα δομημένου εγγράφου ώστε να εμφανίζει ένα συγκεκριμένο τμήμα του προσαρμοσμένου τμήματος XML χρησιμοποιώντας μια έκφραση XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το τροποποιημένο έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save`μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Παράδειγμα πηγαίου κώδικα για το εύρος ετικετών δομημένου εγγράφου Έναρξη αντιστοίχισης Xml με χρήση Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Κατασκευάστε ένα τμήμα XML που περιέχει δεδομένα και προσθέστε το στη συλλογή CustomXmlPart του εγγράφου.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Δημιουργήστε μια StructuredDocumentTag που θα εμφανίζει τα περιεχόμενα του CustomXmlPart στο έγγραφο.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Εάν ορίσουμε μια αντιστοίχιση για το StructuredDocumentTag,
	// θα εμφανίσει μόνο ένα μέρος του CustomXmlPart στο οποίο οδηγεί το XPath.
	// Αυτό το XPath θα δείχνει στο περιεχόμενο του δεύτερου στοιχείου "<text>" του πρώτου στοιχείου "<root>" του CustomXmlPart μας.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Αυτό είναι! Ρυθμίσατε με επιτυχία την αντιστοίχιση XML για μια αρχή εύρους ετικετών δομημένου εγγράφου στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.