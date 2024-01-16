---
title: Κωδικός με εσοχή
linktitle: Κωδικός με εσοχή
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε κώδικα με εσοχή με το Aspose.Words for .NET Βήμα προς βήμα οδηγό.
type: docs
weight: 10
url: /el/net/working-with-markdown/indented-code/
---

Σε αυτό το παράδειγμα, θα εξηγήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα κώδικα με εσοχή με το Aspose.Words για .NET. Ο κώδικας με εσοχή χρησιμοποιείται για την οπτική αναπαράσταση μπλοκ κώδικα με συγκεκριμένη μορφοποίηση.

## Βήμα 1: Χρήση ενός προγράμματος δημιουργίας εγγράφων

Αρχικά, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Βήμα 2: Προσθέστε στυλ για κώδικα με εσοχή

 Θα προσθέσουμε ένα προσαρμοσμένο στυλ για τον κώδικα με εσοχή χρησιμοποιώντας το`Styles.Add` μέθοδος του`Document` αντικείμενο. Σε αυτό το παράδειγμα, δημιουργούμε ένα στυλ που ονομάζεται "IndentedCode" για κώδικα με εσοχή.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Βήμα 3: Προσθήκη κώδικα με εσοχή

Τώρα μπορούμε να προσθέσουμε ένα μπλοκ κώδικα με εσοχή χρησιμοποιώντας το προσαρμοσμένο στυλ "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Παράδειγμα πηγαίου κώδικα για κώδικα με εσοχή με Aspose.Words για .NET

```csharp
// Χρησιμοποιήστε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσετε περιεχόμενο στο έγγραφο.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Συγχαρητήρια ! Τώρα έχετε μάθει πώς να χρησιμοποιείτε τη δυνατότητα κώδικα με εσοχή με το Aspose.Words για .NET.


### Συχνές ερωτήσεις

#### Ε: Τι είναι ο κώδικας με εσοχή στο Markdown;

Α: Ο κώδικας με εσοχή στο Markdown είναι μια μέθοδος μορφοποίησης που χρησιμοποιείται για την εμφάνιση κώδικα σε ένα έγγραφο Markdown. Αποτελείται από την εσοχή κάθε γραμμής κώδικα με κενά ή καρτέλες.

#### Ε: Πώς να χρησιμοποιήσετε τον κώδικα με εσοχή στο Markdown;

Α: Για να χρησιμοποιήσετε τον κώδικα με εσοχή στο Markdown, κάντε εσοχή σε κάθε γραμμή κώδικα με κενά ή καρτέλες.

#### Ε: Ποια είναι τα πλεονεκτήματα του κώδικα με εσοχή στο Markdown;

Α: Ο κώδικας με εσοχή στο Markdown βελτιώνει την αναγνωσιμότητα κώδικα και διευκολύνει την κατανόηση για τους αναγνώστες.

#### Ε: Ποια είναι η διαφορά μεταξύ του κώδικα με εσοχή και των μπλοκ κώδικα στο Markdown;

Α: Ο κώδικας με εσοχή χρησιμοποιείται για μικρά αποσπάσματα κώδικα που εισάγονται στο κείμενο, ενώ τα μπλοκ κώδικα χρησιμοποιούνται για την εμφάνιση μεγαλύτερων τμημάτων κώδικα σε ξεχωριστή μορφοποίηση.

#### Ε: Ο κώδικας με εσοχή στο Markdown υποστηρίζεται από όλους τους συντάκτες του Markdown;

Α: Η υποστήριξη για κώδικα με εσοχή στο Markdown μπορεί να διαφέρει μεταξύ των επεξεργαστών Markdown. Ελέγξτε τη συγκεκριμένη τεκμηρίωση του εκδότη σας για να βεβαιωθείτε.