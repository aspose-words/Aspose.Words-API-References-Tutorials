---
title: Εξαγωγή σε Markdown με ευθυγράμμιση περιεχομένου πίνακα
linktitle: Εξαγωγή σε Markdown με ευθυγράμμιση περιεχομένου πίνακα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εξάγετε περιεχόμενο πίνακα με διαφορετικές στοίχιση σε αρχεία Markdown χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Ακολουθεί ένας οδηγός βήμα προς βήμα για να εξηγήσετε τον ακόλουθο πηγαίο κώδικα C# που βοηθά στην εξαγωγή περιεχομένου σε ένα αρχείο Markdown με στοίχιση περιεχομένου πίνακα χρησιμοποιώντας τη βιβλιοθήκη Aspose.Words για .NET. Βεβαιωθείτε ότι έχετε συμπεριλάβει τη βιβλιοθήκη Aspose.Words στο έργο σας πριν χρησιμοποιήσετε αυτόν τον κώδικα.

## Βήμα 1: Ορισμός διαδρομής καταλόγου εγγράφων

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο των εγγράφων σας όπου θα αποθηκευτεί το επεξεργασμένο έγγραφο.

## Βήμα 2: Δημιουργήστε ένα έγγραφο και μια δημιουργία εγγράφων

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Εδώ δημιουργούμε ένα παράδειγμα του`Document` τάξη και ένα παράδειγμα του`DocumentBuilder` class που θα μας επιτρέψει να χειριστούμε το έγγραφο και να προσθέσουμε στοιχεία.

## Βήμα 3: Εισαγάγετε κελιά στον πίνακα με διαφορετικές στοίχιση παραγράφων

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Χρησιμοποιούμε το Document Builder για να εισαγάγουμε κελιά στον πίνακα και να ορίσουμε διαφορετικές στοίχιση παραγράφων για κάθε κελί.

## Βήμα 4: Ορίστε τις επιλογές εξαγωγής Markdown και αποθηκεύστε το τροποποιημένο έγγραφο

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Ορίζουμε τις επιλογές εξαγωγής Markdown με διαφορετικές στοίχιση περιεχομένου πίνακα και, στη συνέχεια, αποθηκεύουμε το τροποποιημένο έγγραφο χρησιμοποιώντας κάθε επιλογή στοίχισης.

### Παράδειγμα πηγαίου κώδικα για εξαγωγή στο Markdown με στοίχιση περιεχομένου πίνακα χρησιμοποιώντας το Aspose.Words για .NET

```csharp

            
	// Η διαδρομή προς τον κατάλογο εγγράφων.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Κάνει όλες τις παραγράφους μέσα στον πίνακα να ευθυγραμμιστούν.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Η στοίχιση σε αυτή την περίπτωση θα ληφθεί από την πρώτη παράγραφο στην αντίστοιχη στήλη του πίνακα.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Αποθηκεύστε το τροποποιημένο έγγραφο
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
