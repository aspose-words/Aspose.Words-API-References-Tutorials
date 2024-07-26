---
title: Εφαρμογή περιγράμματος περιγράμματος
linktitle: Εφαρμογή περιγράμματος περιγράμματος
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την εφαρμογή περιγράμματος περιγράμματος σε έναν πίνακα χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα για να εφαρμόσετε ένα περίγραμμα περιγράμματος σε έναν πίνακα χρησιμοποιώντας το Aspose.Words για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# και θα σας παρέχουμε έναν ολοκληρωμένο οδηγό που θα σας βοηθήσει να κατανοήσετε και να εφαρμόσετε αυτήν τη δυνατότητα στα δικά σας έργα. Μέχρι το τέλος αυτού του σεμιναρίου, θα έχετε μια σαφή κατανόηση του τρόπου χειρισμού των περιγραμμάτων πίνακα στα έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.

## Βήμα 1: Ορίστε τον κατάλογο εγγράφων
Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο των εγγράφων σας. Εδώ αποθηκεύεται το έγγραφο Word. Αντικαταστήστε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την κατάλληλη διαδρομή.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Ανεβάστε το έγγραφο
 Στη συνέχεια, πρέπει να φορτώσετε το έγγραφο του Word σε μια παρουσία του`Document` τάξη.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Βήμα 3: Πρόσβαση στον πίνακα
 Για να εφαρμόσουμε ένα περίγραμμα περιγράμματος, πρέπει να έχουμε πρόσβαση στον πίνακα του εγγράφου. ο`Table` η κλάση αντιπροσωπεύει έναν πίνακα στο Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Βήμα 4: Ευθυγραμμίστε τον πίνακα στο κέντρο της σελίδας
 Τώρα μπορούμε να ευθυγραμμίσουμε τον πίνακα στο κέντρο της σελίδας χρησιμοποιώντας το`Alignment` ιδιοκτησία του πίνακα.

```csharp
table. Alignment = Table Alignment. Center;
```

## Βήμα 5: Διαγράψτε τα υπάρχοντα περιγράμματα πίνακα
Για να ξεκινήσουμε με ένα νέο περίγραμμα περιγράμματος, πρέπει πρώτα να διαγράψουμε όλα τα υπάρχοντα περιγράμματα από τον πίνακα. Αυτό μπορεί να γίνει χρησιμοποιώντας το`ClearBorders()` μέθοδος.

```csharp
table. ClearBorders();
```

## Βήμα 6: Ορίστε ένα πράσινο περίγραμμα γύρω από τον πίνακα
 Μπορούμε τώρα να ορίσουμε ένα πράσινο περίγραμμα γύρω από το τραπέζι χρησιμοποιώντας το`SetBorder()` μέθοδος για κάθε πλευρά του τραπεζιού. Σε αυτό το παράδειγμα, χρησιμοποιούμε περίγραμμα τύπου "Single" με πάχος 1,5 πόντους και πράσινο χρώμα.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Βήμα 7: Γεμίστε τα κελιά με ένα χρώμα φόντου
Για να βελτιώσουμε την οπτική παρουσίαση του πίνακα, μπορούμε να γεμίσουμε τα κελιά με ένα χρώμα φόντου

ιδέα. Σε αυτό το παράδειγμα, χρησιμοποιούμε ένα ανοιχτό πράσινο χρώμα.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Βήμα 8: Αποθηκεύστε το τροποποιημένο έγγραφο
Τέλος, αποθηκεύουμε το τροποποιημένο έγγραφο σε ένα αρχείο. Μπορείτε να επιλέξετε ένα κατάλληλο όνομα και θέση για το έγγραφο εξόδου.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Συγχαρητήρια ! Τώρα έχετε εφαρμόσει ένα περίγραμμα περιγράμματος σε έναν πίνακα χρησιμοποιώντας το Aspose.Words για .NET.

### Δείγμα πηγαίου κώδικα για Apply Outline Border χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Ευθυγραμμίστε τον πίνακα στο κέντρο της σελίδας.
	table.Alignment = TableAlignment.Center;
	//Διαγράψτε τυχόν υπάρχοντα περιγράμματα από τον πίνακα.
	table.ClearBorders();
	// Τοποθετήστε ένα πράσινο περίγραμμα γύρω από το τραπέζι αλλά όχι μέσα.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Γεμίστε τα κελιά με ανοιχτό πράσινο συμπαγές χρώμα.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να εφαρμόζουμε ένα περίγραμμα περιγράμματος σε έναν πίνακα χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα, μπορείτε εύκολα να ενσωματώσετε αυτή τη λειτουργία στα έργα σας C#. Ο χειρισμός της μορφοποίησης πίνακα είναι μια ουσιαστική πτυχή της επεξεργασίας εγγράφων και το Aspose.Words προσφέρει ένα ισχυρό και ευέλικτο API για να το πετύχει αυτό. Με αυτή τη γνώση, μπορείτε να βελτιώσετε την οπτική παρουσίαση των εγγράφων του Word και να ικανοποιήσετε συγκεκριμένες απαιτήσεις.