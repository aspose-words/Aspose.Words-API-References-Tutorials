---
title: Οριζόντια συγχώνευση
linktitle: Οριζόντια συγχώνευση
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να συγχωνεύετε οριζόντια κελιά σε έναν πίνακα του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/horizontal-merge/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να συγχωνεύουμε οριζόντια κελιά σε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Μέχρι το τέλος αυτού του σεμιναρίου, θα μπορείτε να συγχωνεύετε κελιά οριζόντια στους πίνακες του Word μέσω προγραμματισμού.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Δημιουργία του εγγράφου και προετοιμασία της δημιουργίας εγγράφων
Για να ξεκινήσουμε την επεξεργασία λέξεων με τον πίνακα και τα κελιά, πρέπει να δημιουργήσουμε ένα νέο έγγραφο και να αρχικοποιήσουμε τη δημιουργία εγγράφων. Ακολουθήστε αυτά τα βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Δημιουργήστε το έγγραφο και αρχικοποιήστε τη δημιουργία εγγράφων
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 3: Δημιουργία του πίνακα με οριζόντια συγχώνευση κελιών
Στη συνέχεια, θα δημιουργήσουμε τον πίνακα και θα εφαρμόσουμε οριζόντια συγχώνευση κελιών χρησιμοποιώντας τις ιδιότητες που παρέχονται από το Aspose.Words για .NET. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Αυτό το κελί έχει συγχωνευθεί με το προηγούμενο και θα πρέπει να είναι κενό.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Εδώ χρησιμοποιούμε το εργαλείο δημιουργίας εγγράφων για να δημιουργήσουμε τον πίνακα και να ορίσουμε τις ιδιότητες οριζόντιας συγχώνευσης κελιών. Χρησιμοποιούμε το`HorizontalMerge` ιδιοκτησία του`CellFormat` αντικείμενο για να καθορίσετε τον τύπο οριζόντιας συγχώνευσης που θα εφαρμοστεί σε κάθε κελί. Χρησιμοποιώντας`CellMerge.First` συγχωνεύουμε το πρώτο κελί με το επόμενο, ενώ χρησιμοποιούμε`CellMerge.Previous` συγχωνεύουμε το τρέχον κελί με το προηγούμενο κελί.`CellMerge.None` υποδεικνύει ότι το κελί δεν πρέπει να συγχωνευθεί.

## Βήμα 4: Αποθήκευση του τροποποιημένου εγγράφου
Τέλος, πρέπει να αποθηκεύσουμε το τροποποιημένο έγγραφο με τα κελιά συγχωνευμένα οριζόντια. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για το έγγραφο εξόδου.

### Δείγμα πηγαίου κώδικα για οριζόντια συγχώνευση χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Αυτό το κελί συγχωνεύεται με το προηγούμενο και θα πρέπει να είναι κενό.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να συγχωνεύουμε οριζόντια κελιά σε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να εφαρμόσετε τη συγχώνευση οριζόντιων κελιών στους πίνακες του Word μέσω προγραμματισμού. Αυτή η δυνατότητα σάς επιτρέπει να δημιουργείτε πιο σύνθετες διατάξεις πινάκων και να οργανώνετε καλύτερα τα δεδομένα σας.