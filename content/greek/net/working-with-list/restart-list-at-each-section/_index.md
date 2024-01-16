---
title: Επανεκκινήστε τη λίστα σε κάθε ενότητα
linktitle: Επανεκκινήστε τη λίστα σε κάθε ενότητα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να επαναφέρετε μια αριθμημένη λίστα σε κάθε ενότητα σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-list/restart-list-at-each-section/
---

Σε αυτό το βήμα προς βήμα σεμινάριο, θα σας δείξουμε πώς να επαναφέρετε μια αριθμημένη λίστα σε κάθε ενότητα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα εξηγήσουμε τον παρεχόμενο πηγαίο κώδικα C# και θα σας δείξουμε πώς να τον εφαρμόσετε στα δικά σας έργα.

 Για να ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει το Aspose.Words για .NET στο περιβάλλον ανάπτυξης σας. Εάν δεν το έχετε κάνει ήδη, κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από[Aspose.Releases]https://releases.aspose.com/words/net/.

## Βήμα 1: Δημιουργία του εγγράφου και της λίστας

Αρχικά, δημιουργήστε ένα νέο έγγραφο και προσθέστε μια προεπιλεγμένη αριθμημένη λίστα:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Βήμα 2: Προσθήκη στοιχείων στη λίστα

 Στη συνέχεια χρησιμοποιήστε α`DocumentBuilder` για να προσθέσετε στοιχεία στη λίστα. Μπορείτε να χρησιμοποιήσετε έναν βρόχο για να προσθέσετε πολλά στοιχεία στη λίστα:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

Σε αυτό το παράδειγμα, εισάγουμε μια αλλαγή ενότητας μετά το 15ο στοιχείο λίστας για να δείξουμε την επαναρίθμηση.

## Βήμα 3: Αποθηκεύστε το τροποποιημένο έγγραφο

Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Ετσι ! Έχετε επαναφέρει επιτυχώς μια αριθμημένη λίστα σε κάθε ενότητα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για την επαναφορά της λίστας σε κάθε ενότητα

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Μη διστάσετε να χρησιμοποιήσετε αυτόν τον κώδικα στα δικά σας έργα και να τον τροποποιήσετε ώστε να ταιριάζει στις συγκεκριμένες ανάγκες σας.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να επανεκκινήσω μια λίστα σε κάθε ενότητα στο Aspose.Words;

 Α: Για να επανεκκινήσετε μια λίστα σε κάθε ενότητα στο Aspose.Words, πρέπει να δημιουργήσετε μια παρουσία του`List` τάξη και αντιστοιχίστε σε αυτήν μια αριθμημένη λίστα. Στη συνέχεια, μπορείτε να χρησιμοποιήσετε το`List.IsRestartAtEachSection` ιδιότητα για να καθορίσετε ότι η αρίθμηση θα πρέπει να επανεκκινείται σε κάθε ενότητα. Μπορείτε να συσχετίσετε αυτήν τη λίστα με μία ή περισσότερες ενότητες του εγγράφου σας, έτσι ώστε η αρίθμηση να επανεκκινείται σωστά σε κάθε ενότητα.

#### Ε: Μπορώ να προσαρμόσω τη μορφή αρίθμησης των λιστών στο Aspose.Words;

Α: Ναι, μπορείτε να προσαρμόσετε τη μορφή αρίθμησης των λιστών στο Aspose.Words. ο`List` η class προσφέρει πολλές ιδιότητες για αυτό, όπως`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, κ.λπ. Μπορείτε να χρησιμοποιήσετε αυτές τις ιδιότητες για να ορίσετε τον τύπο της λίστας (με αρίθμηση, με κουκκίδες, κ.λπ.), τη μορφή αρίθμησης (αραβικούς αριθμούς, λατινικούς αριθμούς, γράμματα κ.λπ.) και άλλες επιλογές μορφοποίησης αρίθμησης.

#### Ε: Είναι δυνατόν να προσθέσετε επιπλέον επίπεδα σε μια αριθμημένη λίστα στο Aspose.Words;

 Α: Ναι, είναι δυνατή η προσθήκη επιπλέον επιπέδων σε μια αριθμημένη λίστα στο Aspose.Words. ο`ListLevel` class σάς επιτρέπει να ορίσετε ιδιότητες μορφοποίησης για κάθε επίπεδο της λίστας. Μπορείτε να ορίσετε επιλογές όπως πρόθεμα, επίθημα, στοίχιση, εσοχή κ.λπ. Αυτό σας επιτρέπει να δημιουργείτε λίστες με πολλαπλά επίπεδα ιεραρχίας.