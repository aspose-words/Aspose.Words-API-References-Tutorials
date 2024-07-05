---
title: Χρησιμοποιήστε την πηγή προειδοποίησης
linktitle: Χρησιμοποιήστε την πηγή προειδοποίησης
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε την πηγή προειδοποίησης με το Aspose.Words για .NET Οδηγός βήμα προς βήμα.
type: docs
weight: 10
url: /el/net/working-with-markdown/use-warning-source/
---

Σε αυτό το παράδειγμα, θα σας δείξουμε πώς να χρησιμοποιείτε την πηγή προειδοποίησης με το Aspose.Words για .NET. Η πηγή προειδοποίησης υποδεικνύει την προέλευση της προειδοποίησης όταν χρησιμοποιείτε τη λειτουργία επανάκλησης.

## Βήμα 1: Φόρτωση του εγγράφου

 Θα φορτώσουμε ένα υπάρχον έγγραφο που περιέχει προειδοποιήσεις χρησιμοποιώντας το`Load` μέθοδος του`Document` τάξη.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Βήμα 3: Χρήση της πηγής προειδοποίησης

 Θα χρησιμοποιήσουμε την πηγή προειδοποίησης ορίζοντας την πηγή του εγγράφου`WarningCallback` ιδιοκτησία σε μια συλλογή από`WarningInfo` αντικείμενα.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Βήμα 4: Αποθήκευση του εγγράφου

Τέλος, μπορούμε να αποθηκεύσουμε το έγγραφο στην επιθυμητή μορφή.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Παράδειγμα πηγαίου κώδικα για χρήση προειδοποιητικής πηγής με Aspose.Words για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Συγχαρητήρια ! Τώρα έχετε μάθει πώς να χρησιμοποιείτε την πηγή προειδοποίησης με το Aspose.Words για .NET.

### Συχνές ερωτήσεις

#### Ε: Μπορούμε να προσαρμόσουμε την εμφάνιση της ετικέτας "Προειδοποίηση";

 Α: Η μορφοποίηση της ετικέτας "Προειδοποίηση" εξαρτάται από τη λειτουργία απόδοσης Markdown που χρησιμοποιείται. Στις περισσότερες περιπτώσεις, μπορείτε να προσαρμόσετε την εμφάνιση χρησιμοποιώντας CSS για στόχευση`blockquote` ετικέτα στο έγγραφό σας.

#### Ε: Είναι δυνατή η προσθήκη εικονιδίων στην ετικέτα "Προειδοποίηση";

Α: Ναι, είναι δυνατό να προσθέσετε εικονίδια στην ετικέτα "Προειδοποίηση" χρησιμοποιώντας κώδικα HTML στο έγγραφό σας Markdown. Μπορείτε να εισάγετε ένα`span` ετικέτα με την κατάλληλη κλάση για να εμφανιστεί ένα εικονίδιο δίπλα στο κείμενο προειδοποίησης.

#### Ε: Είναι η ετικέτα "Προειδοποίηση" συμβατή με όλους τους αναγνώστες Markdown;

 Α: Η συμβατότητα της ετικέτας "Προειδοποίηση" εξαρτάται από την απόδοση Markdown που χρησιμοποιείται. Οι περισσότεροι αναγνώστες του Markdown θα υποστηρίξουν το`blockquote` ετικέτα για την εμφάνιση επισημασμένου κειμένου, αλλά η ακριβής εμφάνιση μπορεί να διαφέρει.