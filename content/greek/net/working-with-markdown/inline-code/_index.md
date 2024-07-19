---
title: Ενσωματωμένος κώδικας
linktitle: Ενσωματωμένος κώδικας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ενσωματώνετε κώδικα με το Aspose.Words for .NET Οδηγός βήμα προς βήμα.
type: docs
weight: 10
url: /el/net/working-with-markdown/inline-code/
---

Σε αυτό το παράδειγμα, θα σας καθοδηγήσουμε στον τρόπο χρήσης της δυνατότητας ενσωματωμένου κώδικα με το Aspose.Words για .NET. Ο ενσωματωμένος κώδικας χρησιμοποιείται για την οπτική αναπαράσταση τμημάτων κώδικα μέσα σε μια παράγραφο.

## Βήμα 1: Χρήση ενός προγράμματος δημιουργίας εγγράφων

Αρχικά, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Βήμα 2: Προσθέστε στυλ για ενσωματωμένο κώδικα

 Θα προσθέσουμε ένα προσαρμοσμένο στυλ για τον ενσωματωμένο κώδικα χρησιμοποιώντας το`Styles.Add` μέθοδος του`Document` αντικείμενο. Σε αυτό το παράδειγμα, δημιουργούμε ένα στυλ που ονομάζεται "InlineCode" για ενσωματωμένο κώδικα με προεπιλεγμένο backtick.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Βήμα 3: Προσθέστε ενσωματωμένο κώδικα

Τώρα μπορούμε να προσθέσουμε ενσωματωμένο κώδικα χρησιμοποιώντας το προσαρμοσμένο στυλ "InlineCode". Σε αυτό το παράδειγμα, προσθέτουμε δύο κομμάτια κειμένου με διαφορετικούς αριθμούς backtick.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Παράδειγμα πηγαίου κώδικα για Inline Code με Aspose.Words για .NET

```csharp
// Χρησιμοποιήστε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσετε περιεχόμενο στο έγγραφο.
DocumentBuilder builder = new DocumentBuilder();

// Ο αριθμός των backtick χάθηκε, ένα backtick θα χρησιμοποιηθεί από προεπιλογή.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Θα υπάρχουν 3 backticks.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Συγχαρητήρια ! Τώρα έχετε μάθει πώς να χρησιμοποιείτε τη λειτουργία ενσωματωμένου κώδικα με το Aspose.Words για .NET.


### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να χρησιμοποιήσω τον ενσωματωμένο κώδικα στο Aspose.Words;

Α: Για να χρησιμοποιήσετε ενσωματωμένο κώδικα στο Aspose.Words, μπορείτε να χρησιμοποιήσετε κατάλληλες ετικέτες για να περιβάλλουν το κείμενο που πρόκειται να μορφοποιηθεί ως ενσωματωμένος κώδικας. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε το`<code>` ή`<kbd>` ετικέτα σε κείμενο περιβάλλοντος που θα μορφοποιηθεί ως ενσωματωμένος κώδικας.

#### Ε: Είναι δυνατό να καθοριστεί η γραμματοσειρά ή το χρώμα ενσωματωμένου κώδικα στο Aspose.Words;

 Α: Ναι, μπορείτε να καθορίσετε τη γραμματοσειρά ή το χρώμα του ενσωματωμένου κώδικα στο Aspose.Words. Μπορείτε να χρησιμοποιήσετε το`Font.Name`και`Font.Color` ιδιότητες του`Run` αντικείμενο για να ορίσετε τη γραμματοσειρά και το χρώμα του ενσωματωμένου κώδικα. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε`run.Font.Name = "Courier New"` για να καθορίσετε τη γραμματοσειρά για τον ενσωματωμένο κώδικα και`run.Font.Color = Color.Blue` για να καθορίσετε το χρώμα.

#### Ε: Μπορώ να χρησιμοποιήσω τον ενσωματωμένο κώδικα σε μια παράγραφο που περιέχει άλλα στοιχεία κειμένου;

 Α: Ναι, μπορείτε να χρησιμοποιήσετε τον ενσωματωμένο κώδικα σε μια παράγραφο που περιέχει άλλα στοιχεία κειμένου. Μπορείτε να δημιουργήσετε πολλά`Run` αντικείμενα για να αντιπροσωπεύουν διαφορετικά μέρη της παραγράφου και, στη συνέχεια, χρησιμοποιήστε ετικέτες ενσωματωμένου κώδικα για να μορφοποιήσετε μόνο τα συγκεκριμένα μέρη ως ενσωματωμένο κώδικα. Στη συνέχεια, μπορείτε να τα προσθέσετε στην παράγραφο χρησιμοποιώντας το`Paragraph.AppendChild(run)` μέθοδος.