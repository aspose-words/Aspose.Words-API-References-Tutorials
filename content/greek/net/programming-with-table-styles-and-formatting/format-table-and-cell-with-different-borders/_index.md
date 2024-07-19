---
title: Μορφοποίηση πίνακα και κελιού με διαφορετικά σύνορα
linktitle: Μορφοποίηση πίνακα και κελιού με διαφορετικά σύνορα
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη μορφοποίηση πίνακα και κελιών με διαφορετικά περιγράμματα χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα για τη μορφοποίηση ενός πίνακα και ενός κελιού με διαφορετικά περιθώρια χρησιμοποιώντας το Aspose.Words για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# και θα σας παρέχουμε έναν ολοκληρωμένο οδηγό που θα σας βοηθήσει να κατανοήσετε και να εφαρμόσετε αυτήν τη δυνατότητα στα δικά σας έργα. Στο τέλος αυτού του σεμιναρίου, θα γνωρίζετε πώς να εφαρμόζετε προσαρμοσμένα περιγράμματα σε συγκεκριμένους πίνακες και κελιά στα έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.

## Βήμα 1: Ορίστε τον κατάλογο εγγράφων
Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο των εγγράφων σας. Αυτή είναι η τοποθεσία όπου θέλετε να αποθηκεύσετε το επεξεργασμένο έγγραφο του Word. Αντικαταστήστε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την κατάλληλη διαδρομή.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα νέο πρόγραμμα δημιουργίας εγγράφων και εγγράφων
 Στη συνέχεια, πρέπει να δημιουργήσετε μια νέα παρουσία του`Document` κλάση και έναν κατασκευαστή εγγράφου για αυτό το έγγραφο.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Ξεκινήστε έναν νέο πίνακα και προσθέστε κελιά
Για να ξεκινήσουμε τη δημιουργία του πίνακα, χρησιμοποιούμε το`StartTable()` μέθοδο του προγράμματος δημιουργίας εγγράφων και, στη συνέχεια, προσθέτουμε κελιά στον πίνακα χρησιμοποιώντας το`InsertCell()` μέθοδο και γράφουμε τα περιεχόμενα των κελιών στο χρησιμοποιώντας το`Writeln()` μέθοδος.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
// Ορίστε περιθώρια για ολόκληρο το τραπέζι.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Ορισμός πλήρωσης για αυτό το κελί.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Καθορίστε μια διαφορετική γέμιση κελιών για το δεύτερο κελί.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Διαγραφή μορφοποίησης κελιών από προηγούμενες λειτουργίες.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Δημιουργήστε πιο παχιά περιγράμματα για το πρώτο κελί σε αυτήν τη σειρά. Θα είναι διαφορετικό
// σε σχέση με τα όρια που ορίζονται για τον πίνακα.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Βήμα 4: Αποθηκεύστε το έγγραφο

  τροποποιήθηκε
Τέλος αποθηκεύστε το τροποποιημένο έγγραφο σε ένα αρχείο. Μπορείτε να επιλέξετε ένα κατάλληλο όνομα και θέση για το έγγραφο εξόδου.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Συγχαρητήρια ! Τώρα έχετε μορφοποιήσει έναν πίνακα και ένα κελί με διαφορετικά περιγράμματα χρησιμοποιώντας το Aspose.Words για .NET.

### Δείγμα πηγαίου κώδικα για Μορφοποίηση πίνακα και κελί με διαφορετικά σύνορα χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//Ορίστε τα όρια για ολόκληρο τον πίνακα.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Ορίστε τη σκίαση κελιών για αυτό το κελί.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Καθορίστε μια διαφορετική σκίαση κελιών για το δεύτερο κελί.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Διαγράψτε τη μορφοποίηση κελιών από προηγούμενες λειτουργίες.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Δημιουργήστε μεγαλύτερα περιγράμματα για το πρώτο κελί αυτής της σειράς. Αυτό θα είναι διαφορετικό
// σε σύγκριση με τα όρια που ορίζονται για τον πίνακα.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να μορφοποιούμε έναν πίνακα και ένα κελί με διαφορετικά περιγράμματα χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον αναλυτικό οδηγό, μπορείτε εύκολα να προσαρμόσετε τον πίνακα και τα περιγράμματα κελιών στα έγγραφα του Word. Το Aspose.Words προσφέρει ένα ισχυρό και ευέλικτο API για χειρισμό και μορφοποίηση πινάκων στα έγγραφά σας. Με αυτή τη γνώση, μπορείτε να βελτιώσετε την οπτική παρουσίαση των εγγράφων του Word και να καλύψετε συγκεκριμένες ανάγκες.