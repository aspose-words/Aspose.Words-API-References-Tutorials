---
title: Επαναλάβετε τις σειρές σε επόμενες σελίδες
linktitle: Επαναλάβετε τις σειρές σε επόμενες σελίδες
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να επαναλαμβάνετε σειρές πίνακα σε επόμενες σελίδες σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να επαναλαμβάνουμε τις σειρές ενός πίνακα στις επόμενες σελίδες ενός εγγράφου του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Μέχρι το τέλος αυτού του σεμιναρίου, θα μπορείτε να καθορίσετε σειρές που θα επαναληφθούν στις επόμενες σελίδες του πίνακά σας στα έγγραφα του Word.

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

## Βήμα 3: Δημιουργία του πίνακα με επαναλαμβανόμενες σειρές
Στη συνέχεια, θα δημιουργήσουμε έναν πίνακα με επαναλαμβανόμενες σειρές στις επόμενες σελίδες. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Αρχή του τραπεζιού
builder. StartTable();

// Διαμόρφωση των παραμέτρων της πρώτης γραμμής (γραμμές κεφαλίδας)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Εισαγάγετε το πρώτο κελί της πρώτης σειράς
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Εισαγάγετε το δεύτερο κελί της πρώτης σειράς
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Διαμορφώστε τις παραμέτρους των παρακάτω γραμμών
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Κάντε βρόχο για να εισαγάγετε τα κελιά στις ακόλουθες σειρές
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Τέλος τραπεζιού
builder. EndTable();
```

 Εδώ χρησιμοποιούμε το εργαλείο δημιουργίας εγγράφων για να δημιουργήσουμε έναν πίνακα με δύο σειρές κεφαλίδων και πολλές σειρές δεδομένων. ο`RowFormat.HeadingFormat` Οι παράμετροι χρησιμοποιούνται για τη σήμανση σειρών κεφαλίδων που πρέπει να επαναληφθούν στις επόμενες σελίδες.

## Βήμα 4: Αποθήκευση του τροποποιημένου εγγράφου
Επιτέλους ΗΠΑ

  πρέπει να αποθηκεύσετε το τροποποιημένο έγγραφο με τις σειρές κεφαλίδων να επαναλαμβάνονται στις επόμενες σελίδες του πίνακα. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για το έγγραφο εξόδου.

### Δείγμα πηγαίου κώδικα για επανάληψη σειρών σε επόμενες σελίδες χρησιμοποιώντας Aspose.Words για .NET 

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να επαναλαμβάνουμε τις σειρές ενός πίνακα στις επόμενες σελίδες ενός εγγράφου του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να καθορίσετε ποιες γραμμές θα επαναλάβετε σύμφωνα με τις συγκεκριμένες ανάγκες σας στα έγγραφα του Word.