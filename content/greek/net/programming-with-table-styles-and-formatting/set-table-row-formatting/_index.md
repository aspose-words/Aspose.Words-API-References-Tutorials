---
title: Ορισμός μορφοποίησης σειρών πίνακα
linktitle: Ορισμός μορφοποίησης σειρών πίνακα
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη ρύθμιση της μορφοποίησης σειρών πίνακα χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα για να ορίσετε τη μορφοποίηση σειρών πίνακα χρησιμοποιώντας το Aspose.Words για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# και θα σας παρέχουμε έναν ολοκληρωμένο οδηγό που θα σας βοηθήσει να κατανοήσετε και να εφαρμόσετε αυτήν τη δυνατότητα στα δικά σας έργα. Στο τέλος αυτού του σεμιναρίου, θα ξέρετε πώς να προσαρμόσετε το ύψος και τις επικαλύψεις μιας σειράς πίνακα στα έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.

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

## Βήμα 3: Ξεκινήστε έναν νέο πίνακα και προσθέστε ένα κελί
Για να ξεκινήσουμε τη δημιουργία του πίνακα, χρησιμοποιούμε το`StartTable()` μέθοδο του κατασκευαστή εγγράφου και, στη συνέχεια, προσθέτουμε ένα κελί στον πίνακα χρησιμοποιώντας το`InsertCell()` μέθοδος.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Βήμα 4: Καθορίστε τη μορφοποίηση γραμμής
 Τώρα μπορούμε να ορίσουμε τη μορφοποίηση σειρών προσπελάζοντας το`RowFormat` αντικείμενο του`DocumentBuilder` αντικείμενο. Μπορούμε να ορίσουμε το ύψος της γραμμής και τα περιθώρια (paddings) χρησιμοποιώντας τις αντίστοιχες ιδιότητες.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Βήμα 5: Ορισμός περιθωρίων πίνακα
 Στη συνέχεια, μπορούμε να ορίσουμε τα επιθέματα πίνακα προσπελάζοντας τις αντίστοιχες ιδιότητες του`Table` αντικείμενο. Αυτά τα περιθώρια θα εφαρμοστούν σε όλες τις σειρές του πίνακα.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Βήμα 6: Προσθέστε περιεχόμενο στη σειρά
 Τέλος, μπορούμε να προσθέσουμε περιεχόμενο στη γραμμή χρησιμοποιώντας το πρόγραμμα δημιουργίας εγγράφων`Writeln()` μέθοδος.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Βήμα 7: Ολοκληρώστε τον πίνακα και αποθηκεύστε το έγγραφο
Σε

 Τέλος, τελειώνουμε τη δημιουργία του πίνακα χρησιμοποιώντας το`EndRow()` και`EndTable()` μέθοδο, τότε αποθηκεύουμε το τροποποιημένο έγγραφο σε ένα αρχείο.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Δείγμα πηγαίου κώδικα για Ορισμός μορφοποίησης σειρών πίνακα χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Αυτές οι ιδιότητες μορφοποίησης ορίζονται στον πίνακα και εφαρμόζονται σε όλες τις σειρές του πίνακα.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να ορίζουμε τη μορφοποίηση σειρών πίνακα χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον αναλυτικό οδηγό, μπορείτε εύκολα να προσαρμόσετε το ύψος και τα περιθώρια σειρών πίνακα στα έγγραφά σας Word. Το Aspose.Words προσφέρει ένα ισχυρό και ευέλικτο API για χειρισμό και μορφοποίηση πινάκων στα έγγραφά σας. Με αυτή τη γνώση, μπορείτε να προσαρμόσετε την οπτική διάταξη των τραπεζιών σας στις συγκεκριμένες ανάγκες σας.