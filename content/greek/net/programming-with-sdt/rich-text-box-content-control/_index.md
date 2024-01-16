---
title: Έλεγχος περιεχομένου πλαισίου εμπλουτισμένου κειμένου
linktitle: Έλεγχος περιεχομένου πλαισίου εμπλουτισμένου κειμένου
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε ένα στοιχείο ελέγχου περιεχομένου πλαισίου εμπλουτισμένου κειμένου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET που επιτρέπει τη μορφοποίηση και το στυλ κειμένου.
type: docs
weight: 10
url: /el/net/programming-with-sdt/rich-text-box-content-control/
---

Αυτό το σεμινάριο δείχνει πώς να δημιουργήσετε ένα στοιχείο ελέγχου περιεχομένου πλαισίου εμπλουτισμένου κειμένου σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Τα στοιχεία ελέγχου περιεχομένου πλαισίου εμπλουτισμένου κειμένου επιτρέπουν στους χρήστες να εισάγουν και να μορφοποιούν κείμενο με διάφορα στυλ και επιλογές μορφοποίησης.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα έγγραφο και ένα StructuredDocumentTag
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`StructuredDocumentTag` για την αναπαράσταση του ελέγχου περιεχομένου πλαισίου εμπλουτισμένου κειμένου. Προσδιορίζω`SdtType.RichText` ως ο τύπος και`MarkupLevel.Block` ως επίπεδο σήμανσης για τη δημιουργία πλαισίου εμπλουτισμένου κειμένου σε επίπεδο μπλοκ.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Βήμα 3: Δημιουργήστε και μορφοποιήστε το περιεχόμενο εμπλουτισμένου κειμένου
Δημιουργήστε μια παράγραφο και τρέξτε για να αναπαραστήσετε το περιεχόμενο εμπλουτισμένου κειμένου. Ορίστε τις επιλογές κειμένου και μορφοποίησης όπως χρώμα, γραμματοσειρά κ.λπ.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Βήμα 4: Προσθέστε το περιεχόμενο εμπλουτισμένου κειμένου στο στοιχείο ελέγχου περιεχομένου
Προσθέστε την παράγραφο με το περιεχόμενο εμπλουτισμένου κειμένου στο`ChildNodes` συλλογή του ελέγχου περιεχομένου πλαισίου εμπλουτισμένου κειμένου.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Βήμα 5: Προσθέστε το στοιχείο ελέγχου περιεχομένου στο έγγραφο
 Προσθέστε το στοιχείο ελέγχου περιεχομένου πλαισίου εμπλουτισμένου κειμένου στο σώμα του εγγράφου χρησιμοποιώντας το`AppendChild` μέθοδο του σώματος του πρώτου τμήματος του εγγράφου.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Βήμα 6: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Παράδειγμα πηγαίου κώδικα για τον έλεγχο περιεχομένου πλαισίου εμπλουτισμένου κειμένου χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Αυτό είναι! Δημιουργήσατε με επιτυχία ένα στοιχείο ελέγχου περιεχομένου πλαισίου εμπλουτισμένου κειμένου στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.