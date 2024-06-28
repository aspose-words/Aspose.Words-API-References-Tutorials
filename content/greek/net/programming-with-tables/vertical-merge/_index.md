---
title: Κάθετη συγχώνευση
linktitle: Κάθετη συγχώνευση
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να συγχωνεύετε κάθετα κελιά σε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/vertical-merge/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να συγχωνεύουμε κάθετα κελιά σε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Στο τέλος αυτού του σεμιναρίου, θα μπορείτε να συγχωνεύσετε κάθετα κελιά στους πίνακές σας σε έγγραφα του Word.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Φόρτωση του εγγράφου
Για να ξεκινήσετε την επεξεργασία λέξεων με το έγγραφο, ακολουθήστε τα εξής βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργήστε ένα νέο έγγραφο
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 3: Κατακόρυφη συγχώνευση κελιών
Στη συνέχεια θα συγχωνεύσουμε τα κελιά κάθετα στον πίνακα. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Εισαγάγετε ένα κελί
builder. InsertCell();

// Εφαρμόστε την κατακόρυφη συγχώνευση στο πρώτο κελί
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Εισαγάγετε ένα άλλο κελί
builder. InsertCell();

// Δεν εφαρμόζεται κάθετη συγχώνευση στο κελί
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Εισαγάγετε ένα κελί
builder. InsertCell();

// Εφαρμόστε την κατακόρυφη συγχώνευση με το προηγούμενο κελί
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Εισαγάγετε ένα άλλο κελί
builder. InsertCell();

// Δεν εφαρμόζεται κάθετη συγχώνευση στο κελί
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Τερματίστε τη δημιουργία του πίνακα
builder. EndTable();
```

Σε αυτόν τον κώδικα, χρησιμοποιούμε τον κατασκευαστή DocumentBuilder για να εισάγουμε κελιά σε έναν πίνακα. Εφαρμόζουμε κάθετη συγχώνευση σε κελιά χρησιμοποιώντας την ιδιότητα CellFormat.VerticalMerge. Χρησιμοποιούμε CellMerge.First για την πρώτη συγχώνευση κελιών, CellMerge.Previous για συγχώνευση με το προηγούμενο κελί και CellMerge.None για μη κατακόρυφη συγχώνευση.

## Βήμα 4: Αποθήκευση του τροποποιημένου εγγράφου
Τέλος, πρέπει να αποθηκεύσουμε το τροποποιημένο έγγραφο με τα συγχωνευμένα κελιά. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για το έγγραφο εξόδου.

### Δείγμα πηγαίου κώδικα για κάθετη συγχώνευση χρησιμοποιώντας το Aspose.Words για .NET 
```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Αυτό το κελί είναι κατακόρυφα συγχωνευμένο με το παραπάνω κελί και θα πρέπει να είναι κενό.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να συγχωνεύουμε κάθετα κελιά σε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε εύκολα να συγχωνεύσετε κελιά Κάθετα στους πίνακές σας.