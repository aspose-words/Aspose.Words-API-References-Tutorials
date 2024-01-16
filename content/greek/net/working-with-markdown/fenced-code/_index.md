---
title: Περιφραγμένος Κώδικας
linktitle: Περιφραγμένος Κώδικας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε τη δυνατότητα περιφραγμένου κώδικα με το Aspose.Words για .NET Οδηγός βήμα προς βήμα.
type: docs
weight: 10
url: /el/net/working-with-markdown/fenced-code/
---

Σε αυτό το παράδειγμα, θα σας καθοδηγήσουμε στον τρόπο χρήσης της δυνατότητας περιφραγμένου κώδικα με το Aspose.Words για .NET. Ο περιφραγμένος κώδικας χρησιμοποιείται για την αναπαράσταση μπλοκ κώδικα με συγκεκριμένη μορφοποίηση.

## Βήμα 1: Χρήση ενός προγράμματος δημιουργίας εγγράφων

Αρχικά, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Βήμα 2: Προσθήκη στυλ για περιφραγμένο κώδικα

 Θα προσθέσουμε ένα προσαρμοσμένο στυλ για τον περιφραγμένο κώδικα χρησιμοποιώντας το`Styles.Add` μέθοδος του`Document` αντικείμενο. Σε αυτό το παράδειγμα, δημιουργούμε ένα στυλ που ονομάζεται "FencedCode" για τον περιφραγμένο κώδικα.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Βήμα 3: Προσθήκη περιφραγμένου κώδικα χωρίς πληροφορίες

Τώρα μπορούμε να προσθέσουμε ένα περιφραγμένο μπλοκ κώδικα χωρίς συμβολοσειρά πληροφοριών χρησιμοποιώντας το προσαρμοσμένο στυλ "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Βήμα 4: Προσθέστε περιφραγμένο κώδικα με συμβολοσειρά πληροφοριών

Μπορούμε επίσης να προσθέσουμε ένα περιφραγμένο μπλοκ κώδικα με μια σειρά πληροφοριών χρησιμοποιώντας ένα άλλο προσαρμοσμένο στυλ. Σε αυτό το παράδειγμα, δημιουργούμε ένα στυλ που ονομάζεται "FencedCode.C#" για να αντιπροσωπεύει ένα μπλοκ κώδικα C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Παράδειγμα πηγαίου κώδικα για Περιφραγμένο κώδικα χρησιμοποιώντας Aspose.Words για .NET

```csharp
// Χρησιμοποιήστε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσετε περιεχόμενο στο έγγραφο.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Συχνές ερωτήσεις

#### Ε: Τι είναι ο οριοθετημένος κώδικας στο Markdown;

Α: Ο οριοθετημένος κώδικας στο Markdown είναι μια μέθοδος μορφοποίησης που χρησιμοποιείται για την εμφάνιση κώδικα σε ένα έγγραφο Markdown. Αποτελείται από τη διαμόρφωση του κώδικα με συγκεκριμένους οριοθέτες.

#### Ε: Ποια είναι τα οφέλη του οριοθετημένου κώδικα στο Markdown;

Α: Ο οριοθετημένος κώδικας στο Markdown βελτιώνει την αναγνωσιμότητα του κώδικα και διευκολύνει την κατανόηση για τους αναγνώστες. Επιτρέπει επίσης τη διατήρηση της επισήμανσης σύνταξης σε ορισμένους επεξεργαστές Markdown.

#### Ε: Ποια είναι η διαφορά μεταξύ οριοθετημένου και με εσοχή κώδικα στο Markdown;

Α: Ο οριοθετημένος κώδικας χρησιμοποιεί συγκεκριμένους οριοθέτες για να περικλείει τον κώδικα, ενώ ο κώδικας με εσοχή περιλαμβάνει την εσοχή κάθε γραμμής κώδικα με κενά ή καρτέλες.

#### Ε: Ο οριοθετημένος κώδικας στο Markdown υποστηρίζεται από όλους τους συντάκτες του Markdown;

Α: Η υποστήριξη για οριοθετημένο κώδικα στο Markdown μπορεί να διαφέρει μεταξύ των συντακτών Markdown. Ελέγξτε τη συγκεκριμένη τεκμηρίωση του εκδότη σας για να βεβαιωθείτε.

