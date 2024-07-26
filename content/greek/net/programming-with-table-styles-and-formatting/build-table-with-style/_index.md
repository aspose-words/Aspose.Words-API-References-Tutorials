---
title: Κατασκευή τραπεζιού με στυλ
linktitle: Κατασκευή τραπεζιού με στυλ
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη δημιουργία ενός πίνακα με προσαρμοσμένο στυλ χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα για τη δημιουργία ενός πίνακα με στυλ χρησιμοποιώντας το Aspose.Words για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# και θα σας παρέχουμε έναν ολοκληρωμένο οδηγό που θα σας βοηθήσει να κατανοήσετε και να εφαρμόσετε αυτήν τη δυνατότητα στα δικά σας έργα. Στο τέλος αυτού του σεμιναρίου, θα ξέρετε πώς να δημιουργήσετε έναν πίνακα με προσαρμοσμένο στυλ στα έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.

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

## Βήμα 3: Ξεκινήστε έναν νέο πίνακα και εισαγάγετε ένα κελί
 Για να ξεκινήσουμε την κατασκευή του τραπεζιού, χρησιμοποιούμε το`StartTable()` μέθοδο του προγράμματος δημιουργίας εγγράφων και, στη συνέχεια, εισάγουμε ένα κελί στον πίνακα χρησιμοποιώντας το`InsertCell()` μέθοδος.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
```

## Βήμα 4: Καθορίστε το στυλ του πίνακα
 Τώρα μπορούμε να ορίσουμε το στυλ του πίνακα χρησιμοποιώντας το`StyleIdentifier` ιδιοκτησία. Σε αυτό το παράδειγμα, χρησιμοποιούμε το στυλ "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Βήμα 5: Εφαρμόστε επιλογές στυλ στον πίνακα
 Μπορούμε να καθορίσουμε ποια χαρακτηριστικά θα πρέπει να μορφοποιηθούν με βάση το στυλ χρησιμοποιώντας το`StyleOptions`ιδιότητα του πίνακα. Σε αυτό το παράδειγμα, εφαρμόζουμε τις ακόλουθες επιλογές: "FirstColumn", "RowBands" και "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Βήμα 6: Αυτόματη προσαρμογή του μεγέθους του πίνακα
 Για να προσαρμόσουμε αυτόματα το μέγεθος του πίνακα με βάση τα περιεχόμενά του, χρησιμοποιούμε το`AutoFit()` μέθοδος με το`AutoFitBehavior.AutoFitToContents` η ΣΥΜΠΕΡΙΦΟΡΑ.

```csharp
table.AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Βήμα 7: Προσθήκη περιεχομένου στα κελιά
 Τώρα μπορούμε να προσθέσουμε περιεχόμενο στα κελιά χρησιμοποιώντας το`Writeln()`και`InsertCell()` μεθόδους του προγράμματος δημιουργίας εγγράφων. Σε αυτό το παράδειγμα, προσθέτουμε τις κεφαλίδες για το "Item" και "Quantity (

κιλά)» και τα αντίστοιχα στοιχεία.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writen("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writen("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
```

## Βήμα 8: Αποθηκεύστε το τροποποιημένο έγγραφο
Τέλος, αποθηκεύουμε το τροποποιημένο έγγραφο σε ένα αρχείο. Μπορείτε να επιλέξετε ένα κατάλληλο όνομα και θέση για το έγγραφο εξόδου.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Συγχαρητήρια ! Έχετε πλέον δημιουργήσει έναν πίνακα προσαρμοσμένου στυλ χρησιμοποιώντας το Aspose.Words για .NET.

### Δείγμα πηγαίου κώδικα για Build Table With Style χρησιμοποιώντας Aspose.Words για .NET 

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
// Πρέπει να εισαγάγουμε τουλάχιστον μία σειρά πρώτα πριν ορίσουμε οποιαδήποτε μορφοποίηση πίνακα.
builder.InsertCell();
// Ορίστε το στυλ πίνακα που χρησιμοποιείται με βάση το μοναδικό αναγνωριστικό στυλ.
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
// Εφαρμόστε ποιες λειτουργίες πρέπει να μορφοποιηθούν με βάση το στυλ.
table.StyleOptions =
	TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
table.AutoFit(AutoFitBehavior.AutoFitToContents);
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writeln("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writeln("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργήσουμε έναν πίνακα με στυλ χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα, μπορείτε εύκολα να προσαρμόσετε το στυλ των πινάκων σας στα έγγραφα του Word. Το Aspose.Words προσφέρει ένα ισχυρό και ευέλικτο API για χειρισμό και μορφοποίηση πινάκων στα έγγραφά σας. Με αυτή τη γνώση, μπορείτε να βελτιώσετε την οπτική παρουσίαση των εγγράφων του Word και να καλύψετε συγκεκριμένες ανάγκες.