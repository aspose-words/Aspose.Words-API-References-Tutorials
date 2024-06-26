---
title: Εντονο Κείμενο
linktitle: Εντονο Κείμενο
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε έντονη γραφή με το Aspose.Words for .NET Οδηγός βήμα προς βήμα.
type: docs
weight: 10
url: /el/net/working-with-markdown/bold-text/
---

Σε αυτό το παράδειγμα, θα σας πούμε πώς να κάνετε έντονη γραφή κειμένου με το Aspose.Words για .NET. Το έντονο κείμενο το κάνει πιο ορατό και του δίνει μεγαλύτερη προβολή.

## Βήμα 1: Χρήση ενός προγράμματος δημιουργίας εγγράφων

Αρχικά, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Βήμα 2: Έντονο κείμενο

 Μπορούμε να κάνουμε έντονη γραφή στο κείμενο ορίζοντας το πρόγραμμα δημιουργίας εγγράφων`Font.Bold`ιδιοκτησία σε`true`.

```csharp
builder.Font.Bold = true;
```

## Βήμα 3: Προσθέστε περιεχόμενο στο έγγραφο

 Τώρα μπορούμε να προσθέσουμε περιεχόμενο στο έγγραφο χρησιμοποιώντας τις μεθόδους δημιουργίας εγγράφων, όπως π.χ`Writeln`, το οποίο προσθέτει μια γραμμή κειμένου.

```csharp
builder.Writeln("This text will be bold");
```

## Παράδειγμα Πηγαίος Κώδικας για Έντονα Κείμενα χρησιμοποιώντας Aspose.Words για .NET


```csharp
// Χρησιμοποιήστε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσετε περιεχόμενο στο έγγραφο.
DocumentBuilder builder = new DocumentBuilder();

// Κάντε το κείμενο Έντονο.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

συγχαρητήρια ! Τώρα μάθατε πώς να γράφετε έντονους χαρακτήρες με το Aspose.Words για .NET.


### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να κάνω το κείμενο με έντονη γραφή στο Aspose.Words;

 Α: Για να κάνετε το κείμενο με έντονη γραφή στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`Font.Bold` ιδιοκτησία του`Run`αντικείμενο. Μπορείτε να ορίσετε αυτήν την ιδιότητα σε`true` σε συγκεκριμένο κείμενο με έντονη γραφή. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε`run.Font.Bold=true` για έντονη γραφή του κειμένου μέσα στο`Run` αντικείμενο.

#### Ε: Είναι δυνατόν να σημειωθούν έντονη γραφή πολλών τμημάτων κειμένου στην ίδια παράγραφο;

 Α: Ναι, μπορείτε να κάνετε έντονη γραφή πολλαπλών τμημάτων κειμένου σε μία παράγραφο χρησιμοποιώντας πολλαπλές`Run` αντικείμενα. Μπορείτε να δημιουργήσετε πολλά`Run` αντικείμενα και ορίστε το`Font.Bold`ιδιοκτησία σε`true` για κάθε αντικείμενο να γίνεται έντονη γραφή των επιθυμητών τμημάτων του κειμένου. Στη συνέχεια, μπορείτε να τα προσθέσετε στην παράγραφο χρησιμοποιώντας το`Paragraph.AppendChild(run)` μέθοδος.

#### Ε: Μπορώ να κάνω έντονη γραφή κειμένου που βρίσκεται σε πίνακα ή κελί στο Aspose.Words;

 Α: Ναι, μπορείτε να έχετε έντονη γραφή κειμένου που βρίσκεται σε πίνακα ή κελί στο Aspose.Words. Μπορείτε να πλοηγηθείτε στο κελί ή στην παράγραφο που θέλετε χρησιμοποιώντας τις κατάλληλες μεθόδους και στη συνέχεια να εφαρμόσετε τη μορφοποίηση με έντονη γραφή χρησιμοποιώντας το`Font.Bold` ιδιοκτησία του`Run` ή`Paragraph` αντικείμενο.