---
title: Κρατήστε το τραπέζι μαζί
linktitle: Κρατήστε το τραπέζι μαζί
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να κρατάτε έναν πίνακα μαζί σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/keep-table-together/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να συγκρατούμε έναν πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Μέχρι το τέλος αυτού του σεμιναρίου, θα μπορείτε να διατηρήσετε έναν πίνακα ανέπαφο χωρίς να χωρίζεται σε πολλές σελίδες στα έγγραφα του Word.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Φόρτωση του εγγράφου και ανάκτηση του πίνακα
Για να ξεκινήσουμε την επεξεργασία λέξεων με τον πίνακα, πρέπει να φορτώσουμε το έγγραφο και να ανακτήσουμε τον πίνακα που θέλουμε να διατηρήσουμε μαζί. Ακολουθήστε αυτά τα βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Φορτώστε το έγγραφο
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Ανακτήστε τον πίνακα
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 3: Ενεργοποιήστε την επιλογή "KeepWithNext".
Για να διατηρήσουμε τον πίνακα μαζί και να αποτρέψουμε τον διαχωρισμό του σε πολλές σελίδες, πρέπει να ενεργοποιήσουμε την επιλογή "KeepWithNext" για κάθε παράγραφο του πίνακα εκτός από τις τελευταίες παραγράφους της τελευταίας σειράς του πίνακα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Εδώ κάνουμε βρόχο σε κάθε κελί του πίνακα και ενεργοποιούμε την επιλογή "KeepWithNext" για κάθε παράγραφο στο κελί εκτός από τις τελευταίες παραγράφους της τελευταίας σειράς του πίνακα.

## Βήμα 4: Αποθήκευση του τροποποιημένου εγγράφου
Τέλος, πρέπει να αποθηκεύσουμε το τροποποιημένο έγγραφο με τον πίνακα συγκρατημένο. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για το έγγραφο εξόδου.

### Δείγμα πηγαίου κώδικα για το Keep Table Together χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Πρέπει να ενεργοποιήσουμε το KeepWithNext για κάθε παράγραφο στον πίνακα για να μην σπάσει σε μια σελίδα,
	// εκτός από τις τελευταίες παραγράφους της τελευταίας σειράς του πίνακα.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να κρατάμε έναν πίνακα μαζί σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να διατηρήσετε έναν πίνακα ανέπαφο και να τον αποτρέψετε από το να χωριστεί σε πολλές σελίδες στα έγγραφά σας. Αυτή η δυνατότητα σάς δίνει περισσότερο έλεγχο της εμφάνισης και της διάταξης των πινάκων σας στα έγγραφά σας.