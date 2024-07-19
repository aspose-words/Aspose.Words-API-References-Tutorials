---
title: Αναπτύξτε τη Μορφοποίηση σε κελιά και σε σειρά από στυλ
linktitle: Αναπτύξτε τη Μορφοποίηση σε κελιά και σε σειρά από στυλ
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την επέκταση της μορφοποίησης σε κελιά και σειρές από στυλ πίνακα χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα για την επέκταση της μορφοποίησης σε κελιά και σειρές από ένα στυλ χρησιμοποιώντας το Aspose.Words για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# και θα σας παρέχουμε έναν ολοκληρωμένο οδηγό που θα σας βοηθήσει να κατανοήσετε και να εφαρμόσετε αυτήν τη δυνατότητα στα δικά σας έργα. Στο τέλος αυτού του σεμιναρίου, θα γνωρίζετε πώς να εφαρμόζετε τη μορφοποίηση στυλ πίνακα σε συγκεκριμένα κελιά και σειρές στα έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.


## Βήμα 1: Ορίστε τον κατάλογο εγγράφων
Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο των εγγράφων σας. Εδώ βρίσκεται το έγγραφό σας στο Word. Αντικαταστήστε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την κατάλληλη διαδρομή.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Φορτώστε το υπάρχον έγγραφο
 Στη συνέχεια, πρέπει να φορτώσετε το υπάρχον έγγραφο του Word σε μια παρουσία του`Document` τάξη.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Βήμα 3: Μεταβείτε στο πρώτο κελί του πρώτου πίνακα
 Για να ξεκινήσουμε, πρέπει να πλοηγηθούμε στο πρώτο κελί του πρώτου πίνακα του εγγράφου. Χρησιμοποιούμε το`GetChild()`και`FirstRow.FirstCell` μεθόδους για να λάβετε την αναφορά στο πρώτο κελί.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Βήμα 4: Εμφάνιση αρχικής μορφοποίησης κελιού
Πριν αναπτύξουμε τα στυλ του πίνακα, εμφανίζουμε το τρέχον χρώμα φόντου του κελιού. Αυτό θα πρέπει να είναι κενό επειδή η τρέχουσα μορφοποίηση αποθηκεύεται στο στυλ του πίνακα.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Βήμα 5: Αναπτύξτε τα στυλ πίνακα σε άμεση μορφοποίηση
 Τώρα επεκτείνουμε τα στυλ πίνακα σε άμεση μορφοποίηση χρησιμοποιώντας τα στυλ του εγγράφου`ExpandTableStylesToDirectFormatting()` μέθοδος.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Βήμα 6: Εμφάνιση μορφοποίησης κελιών μετά την επέκταση στυλ
Τώρα εμφανίζουμε το χρώμα φόντου του κελιού μετά την επέκταση των στυλ πίνακα. Ένα μπλε χρώμα φόντου πρέπει να εφαρμοστεί από το στυλ του πίνακα.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Δείγμα πηγαίου κώδικα για Ανάπτυξη μορφοποίησης σε κελιά και γραμμή από στυλ χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Λάβετε το πρώτο κελί του πρώτου πίνακα στο έγγραφο.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Εκτυπώστε πρώτα το χρώμα της σκίασης κελιών.
	// Αυτό θα πρέπει να είναι κενό καθώς η τρέχουσα σκίαση αποθηκεύεται στο στυλ πίνακα.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Τώρα εκτυπώστε τη σκίαση κελιών μετά την επέκταση των στυλ πίνακα.
	// Ένα μπλε χρώμα μοτίβου φόντου θα έπρεπε να έχει εφαρμοστεί από το στυλ του πίνακα.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να επεκτείνουμε τη μορφοποίηση σε κελιά και σειρές από στυλ πίνακα χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα, μπορείτε εύκολα να εφαρμόσετε τη μορφοποίηση στυλ πίνακα σε συγκεκριμένα κελιά και σειρές στα έγγραφα του Word. Το Aspose.Words προσφέρει ένα ισχυρό και ευέλικτο API για χειρισμό και μορφοποίηση πινάκων στα έγγραφά σας. Με αυτή τη γνώση, μπορείτε να προσαρμόσετε περαιτέρω τη διάταξη και την παρουσίαση των εγγράφων του Word.