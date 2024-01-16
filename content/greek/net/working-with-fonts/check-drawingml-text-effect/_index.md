---
title: Ελέγξτε το εφέ κειμένου DrawingML
linktitle: Ελέγξτε το εφέ κειμένου DrawingML
second_title: Aspose.Words Document Processing API
description: Σε αυτό το σεμινάριο, μάθετε πώς να ελέγχετε τα εφέ κειμένου DrawingML σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fonts/check-drawingml-text-effect/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε πώς να ελέγξετε τα εφέ κειμένου DrawingML σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words Library για .NET. Ο έλεγχος των εφέ κειμένου DrawingML σάς επιτρέπει να προσδιορίσετε εάν ένα συγκεκριμένο εφέ εφαρμόζεται σε μέρος του κειμένου. Θα σας οδηγήσουμε βήμα προς βήμα για να σας βοηθήσουμε να κατανοήσετε και να εφαρμόσετε τον κώδικα στο έργο σας .NET.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα στοιχεία:
- Γνώση εργασίας της γλώσσας προγραμματισμού C#
- Η βιβλιοθήκη Aspose.Words για .NET είναι εγκατεστημένη στο έργο σας
- Ένα έγγραφο του Word που περιέχει εφέ κειμένου DrawingML

## Βήμα 1: Ορίστε τον κατάλογο εγγράφων
 Αρχικά, πρέπει να ορίσετε τη διαδρομή καταλόγου στη θέση του εγγράφου του Word. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στον κωδικό με την κατάλληλη διαδρομή.

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο και ελέγξτε τα εφέ κειμένου
Στη συνέχεια, θα φορτώσουμε το έγγραφο του Word και θα αποκτήσουμε πρόσβαση στη συλλογή εκτελέσεων (ακολουθίες χαρακτήρων) στην πρώτη παράγραφο του σώματος του εγγράφου. Στη συνέχεια, θα ελέγξουμε εάν έχουν εφαρμοστεί συγκεκριμένα εφέ κειμένου DrawingML στη γραμματοσειρά της πρώτης εκτέλεσης.

```csharp
// Φορτώστε το έγγραφο
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Ελέγξτε τα εφέ κειμένου DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Δείγμα πηγαίου κώδικα για Έλεγχος εφέ DMLText χρησιμοποιώντας το Aspose.Words για .NET 

```csharp

// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Σε μία εκτέλεση ενδέχεται να εφαρμόζονται πολλά εφέ κειμένου Dml.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## συμπέρασμα
Σε αυτό το σεμινάριο, είδαμε πώς να ελέγξουμε τα εφέ κειμένου DrawingML σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ο έλεγχος των εφέ κειμένου DrawingML σάς επιτρέπει να προσδιορίζετε τμήματα κειμένου που έχουν εφαρμοσμένα συγκεκριμένα εφέ. Μη διστάσετε να χρησιμοποιήσετε αυτήν τη δυνατότητα για να χειριστείτε και να αναλύσετε εφέ κειμένου στα έγγραφα του Word.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να αποκτήσω πρόσβαση σε εφέ κειμένου DrawingML σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words;

Α: Με το Aspose.Words, μπορείτε να αποκτήσετε πρόσβαση σε εφέ κειμένου DrawingML σε ένα έγγραφο του Word χρησιμοποιώντας το παρεχόμενο API. Μπορείτε να περιηγηθείτε σε στοιχεία κειμένου και να ελέγξετε συγκεκριμένες ιδιότητες των εφέ κειμένου, όπως το χρώμα, το μέγεθος κ.λπ.

#### Ε: Ποιοι τύποι εφέ κειμένου DrawingML χρησιμοποιούνται συνήθως σε έγγραφα του Word;

Α: Οι συνήθεις χρησιμοποιούμενοι τύποι εφέ κειμένου DrawingML σε έγγραφα του Word περιλαμβάνουν σκιές, αντανακλάσεις, λάμψεις, διαβαθμίσεις κ.λπ. Αυτά τα εφέ μπορούν να εφαρμοστούν για τη βελτίωση της εμφάνισης και της μορφοποίησης του κειμένου.

#### Ε: Πώς μπορώ να ελέγξω το χρώμα ενός εφέ κειμένου DrawingML σε ένα έγγραφο του Word;

Α: Για να ελέγξετε το χρώμα ενός εφέ κειμένου DrawingML σε ένα έγγραφο του Word, μπορείτε να χρησιμοποιήσετε τις μεθόδους που παρέχονται από το Aspose.Words για να αποκτήσετε πρόσβαση στις ιδιότητες χρώματος του εφέ κειμένου. Με αυτόν τον τρόπο μπορείτε να πάρετε το χρώμα που χρησιμοποιείται για το συγκεκριμένο εφέ κειμένου.

#### Ε: Είναι δυνατός ο έλεγχος των εφέ κειμένου σε έγγραφα του Word που περιέχουν πολλές ενότητες;

Α: Ναι, το Aspose.Words επιτρέπει τον έλεγχο των εφέ κειμένου σε έγγραφα του Word που περιέχουν πολλές ενότητες. Μπορείτε να πλοηγηθείτε σε κάθε ενότητα του εγγράφου και να αποκτήσετε πρόσβαση σε εφέ κειμένου για κάθε ενότητα ξεχωριστά.

#### Ε: Πώς μπορώ να ελέγξω την αδιαφάνεια ενός εφέ κειμένου DrawingML σε ένα έγγραφο του Word;

Α: Για να ελέγξετε την αδιαφάνεια ενός εφέ κειμένου DrawingML σε ένα έγγραφο του Word, μπορείτε να χρησιμοποιήσετε τις μεθόδους που παρέχονται από το Aspose.Words για να αποκτήσετε πρόσβαση στις ιδιότητες αδιαφάνειας του εφέ κειμένου. Αυτό θα σας επιτρέψει να λάβετε την τιμή αδιαφάνειας που εφαρμόζεται στο συγκεκριμένο εφέ κειμένου.