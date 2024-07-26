---
title: Μορφοποιημένος πίνακας
linktitle: Μορφοποιημένος πίνακας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε έναν μορφοποιημένο πίνακα σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/formatted-table/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να δημιουργήσουμε έναν μορφοποιημένο πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Στο τέλος αυτού του σεμιναρίου, θα μπορείτε να δημιουργήσετε πίνακες με προσαρμοσμένη μορφοποίηση στα έγγραφα του Word μέσω προγραμματισμού.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Δημιουργία του εγγράφου και προετοιμασία της δημιουργίας εγγράφων
Για να ξεκινήσουμε τη δημιουργία του μορφοποιημένου πίνακα, πρέπει να δημιουργήσουμε ένα νέο έγγραφο και να αρχικοποιήσουμε τη δημιουργία εγγράφων. Ακολουθήστε αυτά τα βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Δημιουργήστε το έγγραφο και αρχικοποιήστε τη δημιουργία εγγράφων
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 3: Δημιουργία του μορφοποιημένου πίνακα
Στη συνέχεια, θα δημιουργήσουμε τον μορφοποιημένο πίνακα χρησιμοποιώντας τις μεθόδους που παρέχονται από το πρόγραμμα δημιουργίας εγγράφων. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Ξεκινήστε την κατασκευή συστοιχιών
Table table = builder. StartTable();

// Κατασκευή της σειράς κεφαλίδας πίνακα
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Κατασκευή του σώματος της συστοιχίας
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Τέλος κατασκευής συστοιχίας
builder. EndTable();
```

 Εδώ χρησιμοποιούμε το εργαλείο δημιουργίας εγγράφων για να δημιουργήσουμε τον πίνακα βήμα προς βήμα. Ξεκινάμε καλώντας`StartTable()` για να αρχικοποιήσετε τον πίνακα. Στη συνέχεια χρησιμοποιούμε`InsertCell()` για να εισάγετε κελιά και`Write()` για να προσθέσετε περιεχόμενο σε κάθε κελί. Χρησιμοποιούμε επίσης διαφορετικές ιδιότητες μορφοποίησης για να ορίσουμε τη μορφοποίηση σειρών, κελιών και κειμένου πίνακα.

## Βήμα 4: Αποθηκεύστε το έγγραφο
Τέλος, πρέπει να αποθηκεύσουμε το έγγραφο που περιέχει τον μορφοποιημένο πίνακα. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Αποθηκεύστε το έγγραφο
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για το έγγραφο εξόδου.

### Δείγμα πηγαίου κώδικα για Μορφοποιημένο Πίνακα χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Η μορφοποίηση σε επίπεδο πίνακα πρέπει να εφαρμόζεται αφού υπάρχει τουλάχιστον μία σειρά στον πίνακα.
	table.LeftIndent = 20.0;
	// Ορίστε ύψος και ορίστε τον κανόνα ύψους για τη σειρά κεφαλίδας.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Δεν χρειάζεται να καθορίσουμε το πλάτος αυτού του κελιού επειδή έχει κληρονομηθεί από το προηγούμενο κελί.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Επαναφέρετε το ύψος και ορίστε έναν διαφορετικό κανόνα ύψους για το σώμα του τραπεζιού.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Επαναφορά μορφοποίησης γραμματοσειράς.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργήσουμε έναν μορφοποιημένο πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να δημιουργήσετε προσαρμοσμένους πίνακες με συγκεκριμένη μορφοποίηση στα έγγραφα του Word μέσω προγραμματισμού. Αυτή η δυνατότητα σάς επιτρέπει να παρουσιάζετε και να δομείτε τα δεδομένα σας με οπτικά ελκυστικό και οργανωμένο τρόπο.