---
title: Συνδέστε το SDT σε προσαρμοσμένο τμήμα Xml
linktitle: Συνδέστε το SDT σε προσαρμοσμένο τμήμα Xml
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να συνδέετε ένα SDT σε ένα προσαρμοσμένο τμήμα Xml χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Αυτό το σεμινάριο δείχνει πώς να συνδέσετε μια ετικέτα δομημένου εγγράφου (SDT) σε ένα προσαρμοσμένο τμήμα Xml χρησιμοποιώντας το Aspose.Words για .NET. Τα SDT σάς επιτρέπουν να προσθέτετε στοιχεία ελέγχου δομημένου περιεχομένου σε ένα έγγραφο του Word και τα CustomXmlParts παρέχουν έναν τρόπο αποθήκευσης προσαρμοσμένων δεδομένων XML που σχετίζονται με το έγγραφο.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και XML.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα έγγραφο και CustomXmlPart
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`CustomXmlPart` για να αποθηκεύσετε τα προσαρμοσμένα δεδομένα XML. Το προσαρμοσμένο XML πρέπει να είναι σε έγκυρη μορφή XML. Σε αυτό το παράδειγμα, χρησιμοποιούμε μια απλή συμβολοσειρά XML`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Βήμα 3: Προσθέστε μια StructuredDocumentTag (SDT) στο Έγγραφο
 Πρόσθεσε ένα`StructuredDocumentTag`στο έγγραφο για να χρησιμεύσει ως έλεγχος περιεχομένου. Προσδιορίστε το`SdtType` όπως και`PlainText` και το`MarkupLevel` όπως και`Block` για να δημιουργήσετε ένα SDT σε επίπεδο μπλοκ.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Βήμα 4: Ορίστε τη Χαρτογράφηση XML για το SDT
 Αντιστοιχίστε το SDT στο`CustomXmlPart` χρησιμοποιώντας το`SetMapping` μέθοδος του`XmlMapping` ιδιοκτησία. Προσδιορίστε το`CustomXmlPart` , την έκφραση XPath για τον εντοπισμό του επιθυμητού κόμβου XML και το πρόθεμα χώρου ονομάτων εάν είναι απαραίτητο. Σε αυτό το παράδειγμα, αντιστοιχίζουμε το SDT σε`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Βήμα 5: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το τροποποιημένο έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Παράδειγμα πηγαίου κώδικα για Bind Sd Tto Custom Xml Part χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Αυτό είναι! Έχετε συνδέσει με επιτυχία ένα SDT σε ένα CustomXmlPart στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.