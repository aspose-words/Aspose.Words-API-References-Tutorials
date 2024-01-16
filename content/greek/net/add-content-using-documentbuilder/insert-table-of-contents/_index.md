---
title: Εισαγάγετε πίνακα περιεχομένων στο έγγραφο του Word
linktitle: Εισαγάγετε πίνακα περιεχομένων στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισάγετε έναν πίνακα περιεχομένων σε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/add-content-using-documentbuilder/insert-table-of-contents/
---
Σε αυτό το περιεκτικό σεμινάριο, θα μάθετε πώς να εισάγετε έναν πίνακα περιεχομένων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας καθοδηγήσουμε στη διαδικασία και θα σας παρέχουμε τα απαραίτητα αποσπάσματα κώδικα C#. Μέχρι το τέλος αυτού του οδηγού, θα μπορείτε να δημιουργήσετε έναν πίνακα περιεχομένων με τις κατάλληλες επικεφαλίδες και αριθμούς σελίδων.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Η βιβλιοθήκη Aspose.Words for .NET είναι εγκατεστημένη στο σύστημά σας.

## Βήμα 1: Δημιουργήστε ένα νέο Document and DocumentBuilder
Για να ξεκινήσετε, δημιουργήστε ένα νέο έγγραφο χρησιμοποιώντας την κλάση Document και αρχικοποιήστε ένα αντικείμενο DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 2: Εισαγάγετε έναν πίνακα περιεχομένων
Στη συνέχεια, χρησιμοποιήστε τη μέθοδο InsertTableOfContents της κλάσης DocumentBuilder για να εισαγάγετε έναν πίνακα περιεχομένων. Καθορίστε τις απαιτούμενες επιλογές μορφοποίησης στη μέθοδο:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Βήμα 3: Προσθήκη περιεχομένου εγγράφου
Αφού εισαγάγετε τον πίνακα περιεχομένων, προσθέστε το πραγματικό περιεχόμενο του εγγράφου. Ορίστε τα κατάλληλα στυλ επικεφαλίδων χρησιμοποιώντας το StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Βήμα 4: Ενημερώστε τον Πίνακα Περιεχομένων
Ο πίνακας περιεχομένων που εισήχθη πρόσφατα θα είναι αρχικά κενός. Για να το συμπληρώσετε, ενημερώστε τα πεδία στο έγγραφο:

```csharp
doc.UpdateFields();
```

## Βήμα 5: Αποθηκεύστε το έγγραφο
Αφού εισαγάγετε τον πίνακα περιεχομένων και ενημερώσετε τα πεδία, αποθηκεύστε το έγγραφο σε αρχείο χρησιμοποιώντας τη μέθοδο Save της κλάσης Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Παράδειγμα πηγαίου κώδικα για Εισαγωγή πίνακα περιεχομένων με χρήση του Aspose.Words για .NET
Ακολουθεί ο πλήρης πηγαίος κώδικας για την εισαγωγή πίνακα περιεχομένων χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Εκκινήστε το DocumentBuilder με αντικείμενο Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Εισαγωγή πίνακα περιεχομένων
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Ξεκινήστε το πραγματικό περιεχόμενο του εγγράφου στη δεύτερη σελίδα.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Ο πίνακας περιεχομένων που εισήχθη πρόσφατα θα είναι αρχικά κενός.
// Πρέπει να συμπληρωθεί με ενημέρωση των πεδίων στο έγγραφο.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## συμπέρασμα

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να εισάγετε έναν πίνακα περιεχομένων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα, μπορείτε τώρα να δημιουργήσετε έναν πίνακα περιεχομένων με τις κατάλληλες επικεφαλίδες και αριθμούς σελίδων για τα έγγραφά σας.

### Συχνές ερωτήσεις για την εισαγωγή πίνακα περιεχομένων στο έγγραφο του word

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του πίνακα περιεχομένων;

 Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση του πίνακα περιεχομένων τροποποιώντας τις επιλογές μορφοποίησης που καθορίζονται στο`InsertTableOfContents` μέθοδος. Οι παράμετροι σάς επιτρέπουν να ελέγχετε τους αριθμούς σελίδων, την εσοχή και άλλα στυλ.

#### Ε: Τι γίνεται αν θέλω να συμπεριλάβω συγκεκριμένα επίπεδα επικεφαλίδων στον πίνακα περιεχομένων;

 Α: Μπορείτε να καθορίσετε τα επιθυμητά επίπεδα επικεφαλίδων που θα συμπεριληφθούν στον πίνακα περιεχομένων προσαρμόζοντας την τιμή εντός του`InsertTableOfContents` μέθοδος. Για παράδειγμα, χρησιμοποιώντας`"\\o \"1-3\""` θα περιλαμβάνει τα επίπεδα επικεφαλίδων 1 έως 3.

#### Ε: Μπορώ να ενημερώσω αυτόματα τον πίνακα περιεχομένων εάν κάνω αλλαγές στο περιεχόμενο του εγγράφου;

 Α: Ναι, μπορείτε να ενημερώσετε τον πίνακα περιεχομένων αυτόματα καλώντας το`UpdateFields` μέθοδο στο έγγραφο. Αυτό θα διασφαλίσει ότι τυχόν αλλαγές που έγιναν στο περιεχόμενο του εγγράφου, όπως η προσθήκη ή η αφαίρεση επικεφαλίδων, αντικατοπτρίζονται στον πίνακα περιεχομένων.

#### Ε: Πώς μπορώ να διαμορφώσω διαφορετικά τα επίπεδα επικεφαλίδων στον πίνακα περιεχομένων;

 Α: Μπορείτε να διαμορφώσετε διαφορετικά τα επίπεδα επικεφαλίδων χρησιμοποιώντας διαφορετικά στυλ παραγράφου για κάθε επίπεδο επικεφαλίδας. Με την ανάθεση διαφορετικών`StyleIdentifier` αξίες στο`ParagraphFormat` απο`DocumentBuilder`, μπορείτε να δημιουργήσετε ξεχωριστά στυλ για κάθε επίπεδο επικεφαλίδας.

#### Ε: Είναι δυνατή η προσθήκη πρόσθετης μορφοποίησης στις επικεφαλίδες του πίνακα περιεχομένων;

 Α: Ναι, μπορείτε να προσθέσετε πρόσθετη μορφοποίηση στις επικεφαλίδες του πίνακα περιεχομένων, όπως στυλ γραμματοσειράς, χρώματα ή άλλες ιδιότητες. Με την προσαρμογή του`Font` ιδιότητες του`DocumentBuilder`, μπορείτε να εφαρμόσετε προσαρμοσμένη μορφοποίηση στις επικεφαλίδες.