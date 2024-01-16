---
title: Λάβετε θέση πλωτού τραπεζιού
linktitle: Λάβετε θέση πλωτού τραπεζιού
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να λαμβάνετε τη θέση των αιωρούμενων πινάκων σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-tables/get-floating-table-position/
---

Σε αυτό το σεμινάριο, θα μάθουμε πώς να λαμβάνουμε τη θέση ενός αιωρούμενου πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα ακολουθήσουμε έναν οδηγό βήμα προς βήμα για να κατανοήσουμε τον κώδικα και να εφαρμόσουμε αυτήν τη δυνατότητα. Στο τέλος αυτού του σεμιναρίου, θα μπορείτε να λαμβάνετε τις ιδιότητες τοποθέτησης ενός αιωρούμενου πίνακα στα έγγραφα του Word μέσω προγραμματισμού.

## Βήμα 1: Ρύθμιση έργου
1. Εκκινήστε το Visual Studio και δημιουργήστε ένα νέο έργο C#.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.Words για .NET.

## Βήμα 2: Φόρτωση του εγγράφου και πρόσβαση στους πίνακες
Για να ξεκινήσουμε την επεξεργασία λέξεων με πίνακες, πρέπει να φορτώσουμε το έγγραφο που τους περιέχει και να αποκτήσουμε πρόσβαση σε αυτούς. Ακολουθήστε αυτά τα βήματα:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Φορτώστε το έγγραφο
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας. Επίσης, βεβαιωθείτε ότι το έγγραφο περιέχει κυμαινόμενους πίνακες.

## Βήμα 3: Λήψη ιδιοτήτων τοποθέτησης αιωρούμενου πίνακα
Στη συνέχεια, θα κάνουμε κύκλο σε όλους τους πίνακες του εγγράφου και θα λάβουμε τις ιδιότητες τοποθέτησης αιωρούμενου πίνακα. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Εάν ο πίνακας είναι αιωρούμενος τύπος, τότε εκτυπώστε τις ιδιότητες τοποθέτησης του.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Εδώ χρησιμοποιούμε ένα`foreach` βρόχος σε βρόχο σε όλους τους πίνακες του εγγράφου. Ελέγχουμε αν ο πίνακας είναι τύπου float ελέγχοντας το`TextWrapping` ιδιοκτησία. Αν ναι, εκτυπώνουμε τις ιδιότητες τοποθέτησης του πίνακα, όπως οριζόντια άγκυρα, κάθετη άγκυρα, απόλυτες οριζόντιες και κάθετες αποστάσεις, άδεια επικάλυψης, απόλυτη οριζόντια απόσταση και σχετική κάθετη στοίχιση.
 
### Δείγμα πηγαίου κώδικα για Λήψη θέσης κυμαινόμενου πίνακα χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Εάν ο πίνακας είναι κυμαινόμενου τύπου, τότε εκτυπώστε τις ιδιότητες τοποθέτησης του.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να λαμβάνουμε τη θέση ενός αιωρούμενου πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και εφαρμόζοντας τον παρεχόμενο κώδικα C#, μπορείτε να λάβετε μέσω προγραμματισμού τις ιδιότητες τοποθέτησης κυμαινόμενων πινάκων στα έγγραφα του Word. Αυτή η δυνατότητα σάς επιτρέπει να αναλύετε και να χειρίζεστε κυμαινόμενους πίνακες σύμφωνα με τις συγκεκριμένες ανάγκες σας.