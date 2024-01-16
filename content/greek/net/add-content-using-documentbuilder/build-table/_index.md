---
title: Δημιουργία πίνακα σε έγγραφο Word
linktitle: Δημιουργία πίνακα σε έγγραφο Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/add-content-using-documentbuilder/build-table/
---
Σε αυτό το βήμα προς βήμα σεμινάριο, θα μάθετε πώς να δημιουργείτε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας καθοδηγήσουμε στη διαδικασία και θα σας παρέχουμε τα απαραίτητα αποσπάσματα κώδικα C#. Μέχρι το τέλος αυτού του οδηγού, θα μπορείτε να δημιουργήσετε έναν πίνακα με προσαρμοσμένη μορφοποίηση και περιεχόμενο χρησιμοποιώντας την κλάση DocumentBuilder.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Η βιβλιοθήκη Aspose.Words for .NET είναι εγκατεστημένη στο σύστημά σας.

## Βήμα 1: Δημιουργήστε ένα νέο έγγραφο
Για να ξεκινήσετε, δημιουργήστε ένα νέο έγγραφο χρησιμοποιώντας την κλάση Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 2: Ξεκινήστε τον πίνακα
Στη συνέχεια, χρησιμοποιήστε τη μέθοδο StartTable της κλάσης DocumentBuilder για να ξεκινήσετε τη δημιουργία του πίνακα:

```csharp
Table table = builder.StartTable();
```

## Βήμα 3: Εισαγάγετε κελιά και προσθέστε περιεχόμενο
Τώρα, μπορείτε να εισαγάγετε κελιά στον πίνακα και να προσθέσετε περιεχόμενο σε αυτά χρησιμοποιώντας τις μεθόδους InsertCell και Write της κλάσης DocumentBuilder. Προσαρμόστε τη μορφοποίηση κελιών όπως απαιτείται:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Βήμα 4: Τερματίστε τη σειρά
Αφού προσθέσετε περιεχόμενο στα κελιά της πρώτης σειράς, χρησιμοποιήστε τη μέθοδο EndRow της κλάσης DocumentBuilder για να τερματίσετε τη σειρά:

```csharp
builder.EndRow();
```

## Βήμα 5: Προσαρμόστε τη μορφοποίηση σειράς
Μπορείτε να προσαρμόσετε τη μορφοποίηση μιας σειράς ορίζοντας ιδιότητες των αντικειμένων RowFormat και CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Βήμα 6: Τερματίστε τον πίνακα
Για να συμπληρώσετε τον πίνακα, χρησιμοποιήστε τη μέθοδο EndTable της κλάσης DocumentBuilder:

```csharp
builder.EndTable();
```

### Παράδειγμα πηγαίου κώδικα για τη δημιουργία πίνακα χρησιμοποιώντας το Aspose.Words για .NET
Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δημιουργία πίνακα χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να δημιουργείτε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα, μπορείτε τώρα να δημιουργήσετε πίνακες με προσαρμοσμένη μορφοποίηση.

### Συχνές ερωτήσεις για τη δημιουργία πίνακα σε έγγραφο word

#### Ε: Τι είναι το Aspose.Words για .NET;

Α: Το Aspose.Words for .NET είναι μια ισχυρή βιβλιοθήκη επεξεργασίας εγγράφων που επιτρέπει στους προγραμματιστές να δημιουργούν, να διαβάζουν, να επεξεργάζονται και να μετατρέπουν έγγραφα του Microsoft Word μέσω προγραμματισμού σε εφαρμογές .NET. Παρέχει ένα ευρύ φάσμα δυνατοτήτων για εργασία με έγγραφα του Word, όπως επεξεργασία κειμένου, δημιουργία πίνακα, προστασία εγγράφων, μορφοποίηση και άλλα.

#### Ε: Πώς μπορώ να δημιουργήσω έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

Α: Για να δημιουργήσετε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να ακολουθήσετε τα εξής βήματα:
1.  Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`DocumentBuilder` αντικείμενο.
2.  Χρησιμοποιήστε το`StartTable` μέθοδος του`DocumentBuilder`τάξη για να ξεκινήσει η κατασκευή του τραπεζιού.
3.  Εισαγάγετε κελιά στον πίνακα και προσθέστε περιεχόμενο χρησιμοποιώντας το`InsertCell` και`Write` μεθόδους του`DocumentBuilder` τάξη.
4.  Τερματίστε τη σειρά χρησιμοποιώντας το`EndRow` μέθοδος του`DocumentBuilder` τάξη.
5.  Προσαρμόστε τη μορφοποίηση σειρών ορίζοντας τις ιδιότητες του`RowFormat` και`CellFormat` αντικείμενα.
6.  Τερματίστε τον πίνακα χρησιμοποιώντας το`EndTable` μέθοδος του`DocumentBuilder` τάξη.
7. Αποθηκεύστε το έγγραφο.

#### Ε: Πώς μπορώ να προσαρμόσω τη μορφοποίηση του πίνακα και των κελιών του;

 Α: Μπορείτε να προσαρμόσετε τη μορφοποίηση του πίνακα και των κελιών του ορίζοντας διάφορες ιδιότητες του`RowFormat` και`CellFormat` αντικείμενα. Για παράδειγμα, μπορείτε να προσαρμόσετε τη στοίχιση κελιών, τον κατακόρυφο και οριζόντιο προσανατολισμό του κειμένου, το ύψος κελιού, το ύψος της γραμμής και άλλα. Χρησιμοποιώντας αυτές τις ιδιότητες, μπορείτε να επιτύχετε την επιθυμητή εμφάνιση για τον πίνακα και τα περιεχόμενά του.

#### Ε: Μπορώ να δημιουργήσω σύνθετους πίνακες με συγχωνευμένα κελιά και άλλες προηγμένες δυνατότητες;

 Α: Ναι, το Aspose.Words για .NET παρέχει προηγμένες δυνατότητες για τη δημιουργία πολύπλοκων πινάκων, συμπεριλαμβανομένης της υποστήριξης για συγχωνευμένα κελιά, ένθετους πίνακες και σύνθετες διατάξεις πινάκων. Μπορείτε να χρησιμοποιήσετε το`MergeCells` μέθοδος συγχώνευσης κελιών,`StartTable`μέθοδο για τη δημιουργία ένθετων πινάκων και άλλες μεθόδους για την επίτευξη της επιθυμητής δομής πίνακα.

#### Ε: Είναι το Aspose.Words για .NET συμβατό με διαφορετικές μορφές εγγράφων του Word;

Α: Ναι, το Aspose.Words για .NET είναι συμβατό με διάφορες μορφές εγγράφων του Word, συμπεριλαμβανομένων των DOC, DOCX, RTF και άλλων. Υποστηρίζει τόσο μορφές παλαιού τύπου (DOC) όσο και σύγχρονες μορφές που βασίζονται σε XML (DOCX) και σας επιτρέπει να εργάζεστε με έγγραφα σε διαφορετικές μορφές χωρίς προβλήματα.

#### Ε: Πού μπορώ να βρω περισσότερες πληροφορίες και τεκμηρίωση για το Aspose.Words για .NET;

 Α: Μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και παραδείγματα κώδικα[Αναφορές API](https://reference.aspose.com/words/net/). Η τεκμηρίωση θα παρέχει λεπτομερείς πληροφορίες σχετικά με τις δυνατότητες της βιβλιοθήκης και τον τρόπο χρήσης τους στις εφαρμογές σας .NET.