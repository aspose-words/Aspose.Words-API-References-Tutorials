---
title: Εισαγάγετε τον πίνακα απευθείας
linktitle: Εισαγάγετε τον πίνακα απευθείας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισάγετε έναν πίνακα απευθείας σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/insert-table-directly/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να εισάγετε απευθείας έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Μέχρι το τέλος αυτού του σεμιναρίου, θα μπορείτε να εισάγετε πίνακες απευθείας στα έγγραφα του Word μέσω προγραμματισμού.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Δημιουργία εγγράφου και πίνακα
Για να ξεκινήσουμε την επεξεργασία λέξεων με τον πίνακα, πρέπει να δημιουργήσουμε ένα νέο έγγραφο και να αρχικοποιήσουμε τον πίνακα. Ακολουθήστε αυτά τα βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργία εγγράφου
Document doc = new Document();

//Δημιουργήστε τον πίνακα
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 3: Δημιουργία του πίνακα
Στη συνέχεια, θα δημιουργήσουμε τον πίνακα προσθέτοντας σειρές και κελιά. Χρησιμοποιήστε τον ακόλουθο κώδικα ως παράδειγμα:

```csharp
// Δημιουργήστε την πρώτη σειρά
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Δημιουργήστε το πρώτο κελί
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Αντιγράψτε το κελί για το δεύτερο κελί της σειράς
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Εδώ δημιουργούμε μια σειρά με το`AllowBreakAcrossPages` ιδιοκτησία ορίζεται σε`true` για να επιτρέπεται η αλλαγή σελίδας μεταξύ σειρών. Στη συνέχεια, δημιουργούμε ένα κελί με έγχρωμο φόντο, σταθερό πλάτος και καθορισμένο περιεχόμενο κειμένου. Στη συνέχεια, αντιγράφουμε αυτό το κελί για να δημιουργήσουμε το δεύτερο κελί στη σειρά.

## Βήμα 4: Αυτόματη προσαρμογή πίνακα
Μπορούμε να εφαρμόσουμε αυτόματες προσαρμογές στον πίνακα για να τον μορφοποιήσουμε σωστά. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Αυτή η γραμμή κώδικα εφαρμόζει μια αυτόματη προσαρμογή που βασίζεται σε σταθερά πλάτη στηλών.

## Βήμα 5: Εγγραφή του

  τροποποιημένο έγγραφο
Τέλος, πρέπει να αποθηκεύσουμε το τροποποιημένο έγγραφο με απευθείας εισαγωγή του πίνακα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για το έγγραφο εξόδου.

### Δείγμα πηγαίου κώδικα για Εισαγωγή πίνακα απευθείας χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Ξεκινάμε δημιουργώντας το αντικείμενο του πίνακα. Σημειώστε ότι πρέπει να περάσουμε το αντικείμενο εγγράφου
	//στον κατασκευαστή κάθε κόμβου. Αυτό συμβαίνει γιατί κάθε κόμβος που δημιουργούμε πρέπει να ανήκει
	// σε κάποιο έγγραφο.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Εδώ θα μπορούσαμε να καλέσουμε το EnsureMinimum για να δημιουργήσουμε τις σειρές και τα κελιά για εμάς. Αυτή η μέθοδος χρησιμοποιείται
	// για να διασφαλίσετε ότι ο καθορισμένος κόμβος είναι έγκυρος. Σε αυτήν την περίπτωση, ένας έγκυρος πίνακας θα πρέπει να έχει τουλάχιστον μία γραμμή και ένα κελί.
	// Αντίθετα, θα χειριστούμε μόνοι μας τη δημιουργία της σειράς και του πίνακα.
	// Αυτός θα ήταν ο καλύτερος τρόπος για να γίνει αυτό εάν δημιουργούσαμε έναν πίνακα μέσα σε έναν αλγόριθμο.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Μπορούμε πλέον να εφαρμόσουμε οποιεσδήποτε ρυθμίσεις αυτόματης προσαρμογής.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Στη συνέχεια θα επαναλάβαμε τη διαδικασία για τα άλλα κελιά και σειρές του πίνακα.
	// Μπορούμε επίσης να επιταχύνουμε τα πράγματα κλωνοποιώντας υπάρχοντα κελιά και σειρές.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να εισάγουμε απευθείας έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον αναλυτικό οδηγό και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να εισαγάγετε πίνακες απευθείας στα έγγραφα του Word μέσω προγραμματισμού. Αυτή η δυνατότητα σάς επιτρέπει να δημιουργείτε και να προσαρμόζετε πίνακες σύμφωνα με τις συγκεκριμένες ανάγκες σας.