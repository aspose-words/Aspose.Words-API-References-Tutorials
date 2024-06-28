---
title: Προτιμώμενες ρυθμίσεις πλάτους
linktitle: Προτιμώμενες ρυθμίσεις πλάτους
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ορίζετε τα προτιμώμενα πλάτη κελιών πίνακα σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/preferred-width-settings/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να ορίζουμε τις προτιμώμενες ρυθμίσεις πλάτους για κελιά πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Μέχρι το τέλος αυτού του σεμιναρίου, θα μπορείτε να καθορίσετε διαφορετικά προτιμώμενα πλάτη για τα κελιά του πίνακα στα έγγραφα του Word.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Δημιουργία του εγγράφου και προετοιμασία της δημιουργίας εγγράφων
Για να ξεκινήσετε την επεξεργασία λέξεων με τη δημιουργία εγγράφων και εγγράφων, ακολουθήστε τα εξής βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργία εγγράφου
Document doc = new Document();

// Αρχικοποιήστε τη δημιουργία εγγράφων
DocumentBuilder builder = new DocumentBuilder(doc);
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 3: Κατασκευή του πίνακα με τα προτιμώμενα πλάτη
Στη συνέχεια, θα δημιουργήσουμε έναν πίνακα με τρία κελιά που έχουν διαφορετικά προτιμώμενα πλάτη. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Αρχή του τραπεζιού
builder. StartTable();

// Εισαγάγετε ένα κελί απόλυτου μεγέθους
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Εισαγάγετε ένα κελί σχετικού μεγέθους (σε ποσοστό)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Εισαγάγετε ένα κελί αυτόματου μεγέθους
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Τέλος τραπεζιού
builder. EndTable();
```

Εδώ χρησιμοποιούμε το εργαλείο δημιουργίας εγγράφων για να δημιουργήσουμε έναν πίνακα με τρία κελιά. Το πρώτο κελί έχει ένα προτιμώμενο πλάτος 40 σημείων, το δεύτερο κελί έχει ένα προτιμώμενο πλάτος 20% του πλάτους του πίνακα και το τρίτο κελί έχει ένα αυτόματο προτιμώμενο πλάτος που προσαρμόζεται.

  ανάλογα με τον διαθέσιμο χώρο.

## Βήμα 4: Αποθήκευση του τροποποιημένου εγγράφου
Τέλος, πρέπει να αποθηκεύσουμε το τροποποιημένο έγγραφο με τις προτιμώμενες ρυθμίσεις πλάτους που έχουν οριστεί για τα κελιά του πίνακα. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για το έγγραφο εξόδου.

### Δείγμα πηγαίου κώδικα για τις προτιμώμενες ρυθμίσεις πλάτους χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Εισαγάγετε μια σειρά πίνακα που αποτελείται από τρία κελιά που έχουν διαφορετικά προτιμώμενα πλάτη.
	builder.StartTable();
	// Εισαγάγετε ένα κελί απόλυτου μεγέθους.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Εισαγάγετε ένα κελί σχετικού μεγέθους (ποσοστό).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Εισαγάγετε ένα κελί σε αυτόματο μέγεθος.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να ορίζουμε τις προτιμώμενες ρυθμίσεις πλάτους για κελιά πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να προσαρμόσετε τα πλάτη των κελιών του πίνακα στις συγκεκριμένες ανάγκες σας στα έγγραφα του Word.