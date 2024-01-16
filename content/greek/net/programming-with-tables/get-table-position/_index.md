---
title: Λήψη θέσης τραπεζιού
linktitle: Λήψη θέσης τραπεζιού
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να βρείτε τη θέση ενός πίνακα σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/get-table-position/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να λαμβάνουμε τη θέση ενός πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Στο τέλος αυτού του σεμιναρίου, θα μπορείτε να λαμβάνετε ιδιότητες τοποθέτησης πίνακα στα έγγραφα του Word μέσω προγραμματισμού.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Φόρτωση του εγγράφου και πρόσβαση στον πίνακα
Για να ξεκινήσουμε την επεξεργασία λέξεων με τον πίνακα, πρέπει να φορτώσουμε το έγγραφο που το περιέχει και να αποκτήσουμε πρόσβαση σε αυτό. Ακολουθήστε αυτά τα βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Φορτώστε το έγγραφο
Document doc = new Document(dataDir + "Tables.docx");

// Πρόσβαση στη συστοιχία
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας. Επίσης, βεβαιωθείτε ότι το έγγραφο περιέχει τον πίνακα του οποίου τη θέση θέλετε να λάβετε.

## Βήμα 3: Λήψη ιδιοτήτων τοποθέτησης πίνακα
Στη συνέχεια, θα ελέγξουμε τον τύπο τοποθέτησης του πίνακα και θα λάβουμε τις κατάλληλες ιδιότητες τοποθέτησης. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Εδώ χρησιμοποιούμε μια συνθήκη για να ελέγξουμε αν ο πίνακας είναι τύπου float. Αν ναι, εκτυπώνουμε το`RelativeHorizontalAlignment` και`RelativeVerticalAlignment` ιδιότητες για να λάβετε τη σχετική οριζόντια και κάθετη στοίχιση του πίνακα. Διαφορετικά, εκτυπώνουμε το`Alignment` ιδιότητα για να λάβετε την ευθυγράμμιση του πίνακα.

### Δείγμα πηγαίου κώδικα για Λήψη θέσης πίνακα χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να λαμβάνουμε τη θέση ενός πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να λάβετε τις ιδιότητες θέσης πίνακα στα έγγραφά σας Word μέσω προγραμματισμού. Αυτή η δυνατότητα σάς επιτρέπει να αναλύετε και να χειρίζεστε πίνακες σύμφωνα με τις συγκεκριμένες θέσεις τους.