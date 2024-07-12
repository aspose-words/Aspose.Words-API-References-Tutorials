---
title: Υπογραμμίσεις
linktitle: Υπογραμμίσεις
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε τονισμό (έντονα και πλάγια γράμματα) με το Aspose.Words for .NET Βήμα προς βήμα οδηγό.
type: docs
weight: 10
url: /el/net/working-with-markdown/emphases/
---

Σε αυτό το παράδειγμα, θα εξηγήσουμε πώς να χρησιμοποιήσουμε τις υπογραμμίσεις με το Aspose.Words για .NET. Οι υπογραμμίσεις χρησιμοποιούνται για να τονιστούν ορισμένα μέρη του κειμένου, όπως έντονη γραφή και πλάγια γραφή.

## Βήμα 1: Αρχικοποίηση εγγράφου

 Αρχικά, θα αρχικοποιήσουμε το έγγραφο δημιουργώντας μια παρουσία του`Document` τάξη.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Βήμα 2: Χρήση μιας γεννήτριας εγγράφων

Στη συνέχεια, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Προσθέστε κείμενο με Υπογραμμίσεις

Μπορούμε να προσθέσουμε κείμενο έμφασης αλλάζοντας τις ιδιότητες γραμματοσειράς της δημιουργίας εγγράφων. Σε αυτό το παράδειγμα, χρησιμοποιούμε έντονους και πλάγιους χαρακτήρες για να τονίσουμε διαφορετικά μέρη του κειμένου.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Βήμα 4: Αποθήκευση του εγγράφου

 Τέλος, μπορούμε να αποθηκεύσουμε το έγγραφο στην επιθυμητή μορφή. Σε αυτό το παράδειγμα, χρησιμοποιούμε το`.md` επέκταση για μια μορφή Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Συγχαρητήρια ! Τώρα μάθατε πώς να χρησιμοποιείτε έμφαση με το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για Emphases χρησιμοποιώντας Aspose.Words για .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να επισημάνω κείμενο χρησιμοποιώντας το Markdown;

Α: Για να επισημάνετε κείμενο χρησιμοποιώντας το Markdown, απλώς περιβάλετε το κείμενο με τα κατάλληλα σύμβολα. Χρήση`*` ή`_` για πλάγιους χαρακτήρες,`**` ή`__` για τολμηρές, και`~~` για διαγραφή.

#### Ε: Μπορούμε να συνδυάσουμε διαφορετικά σημεία στο ίδιο κείμενο;

 Α: Ναι, είναι δυνατός ο συνδυασμός διαφορετικών επισημάνσεων στο ίδιο κείμενο. Για παράδειγμα, μπορείτε να κάνετε έντονη και πλάγια γραφή σε μια λέξη χρησιμοποιώντας και τα δύο`**`και`*` γύρω από τη λέξη.

#### Ε: Ποιες επιλογές επισήμανσης είναι διαθέσιμες στο Markdown;

Α: Οι επιλογές επισήμανσης που είναι διαθέσιμες στο Markdown είναι πλάγιες (`*` ή`_`), τολμηρός (`**` ή`__`), και διαγράμμιση (`~~`).

#### Ε: Πώς χειρίζομαι περιπτώσεις όπου το κείμενο περιέχει ειδικούς χαρακτήρες που χρησιμοποιούνται από τον Markdown για επισήμανση;

 Α: Εάν το κείμενό σας περιέχει ειδικούς χαρακτήρες που χρησιμοποιούνται από τον Markdown για επισήμανση, μπορείτε να διαφύγετε από αυτούς τοποθετώντας πριν από αυτούς ένα`\` . Για παράδειγμα,`\*` θα εμφανίσει έναν κυριολεκτικό αστερίσκο.

#### Ε: Μπορούμε να προσαρμόσουμε την εμφάνιση της επισήμανσης χρησιμοποιώντας CSS;

Α: Η επισήμανση στο Markdown συνήθως αποδίδεται χρησιμοποιώντας τα προεπιλεγμένα στυλ του προγράμματος περιήγησης. Εάν μετατρέψετε το Markdown σε HTML, μπορείτε να προσαρμόσετε την εμφάνιση της επισήμανσης χρησιμοποιώντας κανόνες CSS.