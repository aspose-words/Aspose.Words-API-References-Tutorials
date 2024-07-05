---
title: Παραθέτω, αναφορά
linktitle: Παραθέτω, αναφορά
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε το quote με το Aspose.Words for .NET Οδηγός βήμα προς βήμα.
type: docs
weight: 10
url: /el/net/working-with-markdown/quote/
---

Σε αυτό το παράδειγμα, θα εξηγήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα προσφοράς με το Aspose. Τα λόγια για .NET Quote χρησιμοποιούνται για την επισήμανση τμημάτων κειμένου περιβάλλοντάς τα με ένα ειδικό περίγραμμα.

## Βήμα 1: Χρήση ενός προγράμματος δημιουργίας εγγράφων

Αρχικά, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Βήμα 2: Χρήση του προεπιλεγμένου στυλ αναφοράς

Θα χρησιμοποιήσουμε το προεπιλεγμένο στυλ παραγράφου που ονομάζεται "Παράθεση" για να εφαρμόσουμε μορφοποίηση εισαγωγικών στο κείμενο.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Βήμα 3: Δημιουργία στυλ για ένθετα επίπεδα

 Μπορούμε να δημιουργήσουμε στυλ για ένθετα επίπεδα χρησιμοποιώντας το`Styles.Add` μέθοδος του`Document` αντικείμενο. Σε αυτό το παράδειγμα, δημιουργούμε ένα στυλ που ονομάζεται "Quote1" για να αντιπροσωπεύει ένα ένθετο επίπεδο προσφοράς.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Παράδειγμα πηγαίου κώδικα για αναφορές με Aspose.Words για .NET


```csharp
// Χρησιμοποιήστε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσετε περιεχόμενο στο έγγραφο.
DocumentBuilder builder = new DocumentBuilder();

// Από προεπιλογή, ένα έγγραφο αποθηκεύει το στυλ μπλοκ εισαγωγικών για το πρώτο επίπεδο.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Δημιουργήστε στυλ για ένθετα επίπεδα μέσω της κληρονομιάς στυλ.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Συγχαρητήρια ! Τώρα έχετε μάθει πώς να χρησιμοποιείτε τη δυνατότητα παραπομπών με το Aspose.Words για .NET.


### Συχνές ερωτήσεις

#### Ε: Τι είναι μια αναφορά στο Markdown;

Α: Ένα απόσπασμα στο Markdown είναι ένας τρόπος για να επισημάνετε αποσπάσματα κειμένου από άλλες πηγές ή να παραπέμψετε διάσημα αποσπάσματα.

#### Ε: Πώς να χρησιμοποιήσετε εισαγωγικά στο Markdown;

Α: Για να χρησιμοποιήσετε ένα απόσπασμα στο Markdown, εσωκλείστε το κείμενο του εισαγωγικού σε αγκύλες (`>`). Κάθε γραμμή της παραπομπής πρέπει να ξεκινά με ένα chevron.

#### Ε: Τα εισαγωγικά Markdown υποστηρίζουν χαρακτηριστικά;

Α: Οι αναφορές Markdown δεν υποστηρίζουν συγκεκριμένα χαρακτηριστικά. Απλώς επισημαίνονται από τη μορφοποίηση του παρατιθέμενου κειμένου.

#### Ε: Μπορείτε να ενσωματώσετε εισαγωγικά στο Markdown;

Α: Ναι, είναι δυνατό να τοποθετηθούν εισαγωγικά στο Markdown προσθέτοντας ένα επιπλέον επίπεδο γωνιακών αγκύλων (`>`).