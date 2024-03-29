---
title: Ορίστε την έκδοση Ms Word
linktitle: Ορίστε την έκδοση Ms Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να φορτώνετε ένα έγγραφο με μια καθορισμένη έκδοση του MS Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-loadoptions/set-ms-word-version/
---
Κατά την επεξεργασία λέξεων με έγγραφα Word σε μια εφαρμογή C#, μπορεί να είναι απαραίτητο να καθορίσετε την έκδοση του Microsoft Word που θα χρησιμοποιηθεί κατά τη φόρτωση του εγγράφου. Με τη βιβλιοθήκη Aspose.Words για .NET, μπορείτε εύκολα να ορίσετε ποια έκδοση του MS Word να χρησιμοποιείτε χρησιμοποιώντας το LoadOptions. Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας καθοδηγήσουμε πώς να χρησιμοποιήσετε τον πηγαίο κώδικα του Aspose.Words για .NET C# για τη φόρτωση ενός εγγράφου με μια καθορισμένη έκδοση του MS Word χρησιμοποιώντας τις επιλογές φόρτωσης LoadOptions.

## Κατανόηση της βιβλιοθήκης Aspose.Words

Πριν βουτήξετε στον κώδικα, είναι σημαντικό να κατανοήσετε τη βιβλιοθήκη Aspose.Words για το .NET. Το Aspose.Words είναι μια ισχυρή βιβλιοθήκη για τη δημιουργία, επεξεργασία, μετατροπή και προστασία εγγράφων του Word σε διαφορετικές πλατφόρμες, συμπεριλαμβανομένου του .NET. Προσφέρει πολλές δυνατότητες χειρισμού εγγράφων, όπως εισαγωγή κειμένου, αλλαγή μορφοποίησης, προσθήκη ενοτήτων και πολλά άλλα.

## Διαμόρφωση επιλογών φόρτωσης

Το πρώτο βήμα είναι να διαμορφώσουμε τις επιλογές φόρτωσης για το έγγραφό μας. Χρησιμοποιήστε την κλάση LoadOptions για να καθορίσετε τις παραμέτρους φόρτωσης. Στην περίπτωσή μας, πρέπει να ορίσουμε την ιδιότητα MswVersion στην επιθυμητή έκδοση του MS Word. Για παράδειγμα, χρησιμοποιούμε την έκδοση του Microsoft Word 2010. Εδώ είναι πώς να το κάνετε:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Δημιουργούμε ένα νέο αντικείμενο LoadOptions και ορίζουμε την ιδιότητα MswVersion σε MsWordVersion.Word2010 για να καθορίσουμε την έκδοση του MS Word 2010.

## Φόρτωση εγγράφου με καθορισμένη έκδοση του MS Word

Τώρα που έχουμε διαμορφώσει τις επιλογές φόρτωσης, μπορούμε να φορτώσουμε το έγγραφο χρησιμοποιώντας την κλάση Document και να καθορίσουμε τις επιλογές φόρτωσης. Εδώ είναι ένα παράδειγμα:

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Σε αυτό το παράδειγμα, φορτώνουμε το έγγραφο "Document.docx" που βρίσκεται στον κατάλογο εγγράφων χρησιμοποιώντας τις καθορισμένες επιλογές φόρτωσης.

### Παράδειγμα πηγαίου κώδικα για LoadOptions με λειτουργικότητα "Set MS Word Version" χρησιμοποιώντας Aspose.Words για .NET

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Διαμορφώστε τις επιλογές φόρτωσης με τη δυνατότητα "Ορισμός έκδοσης MS Word".
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Φορτώστε το έγγραφο με την καθορισμένη έκδοση του MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Αποθηκεύστε το έγγραφο
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## συμπέρασμα

Σε αυτόν τον οδηγό, έχουμε εξηγήσει πώς να ανεβάσετε ένα έγγραφο που καθορίζει μια συγκεκριμένη έκδοση του MS Word χρησιμοποιώντας τη βιβλιοθήκη Aspose.Words για .NET. Ακολουθώντας τα παρεχόμενα βήματα και χρησιμοποιώντας την πηγή κώδικα C# που παρέχεται, μπορείτε εύκολα να εφαρμόσετε αυτήν τη λειτουργία στην εφαρμογή σας C#. Η φόρτωση ενός εγγράφου με μια καθορισμένη έκδοση του MS Word σάς επιτρέπει να διασφαλίσετε τη σωστή συμβατότητα και επεξεργασία του εγγράφου στην εφαρμογή σας.


### Συχνές ερωτήσεις

#### Ε: Γιατί θα χρειαστεί να καθορίσω την έκδοση του MS Word κατά τη φόρτωση ενός εγγράφου σε μια εφαρμογή C#;

Ο καθορισμός της έκδοσης του MS Word διασφαλίζει τη σωστή φόρτωση και επεξεργασία του εγγράφου, ειδικά όταν πρόκειται για συγκεκριμένη μορφοποίηση ή δυνατότητες που ενδέχεται να διαφέρουν μεταξύ διαφορετικών εκδόσεων.

#### Ε: Ποιες εκδόσεις του MS Word υποστηρίζει το Aspose.Words;

Α: Το Aspose.Words για .NET υποστηρίζει διάφορες εκδόσεις του MS Word, συμπεριλαμβανομένων των Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 και άλλων.

#### Ε: Μπορώ να φορτώσω ένα έγγραφο με διαφορετική έκδοση του MS Word από αυτή που είναι εγκατεστημένη στο σύστημά μου;

Α: Ναι, το Aspose.Words σάς επιτρέπει να καθορίσετε μια διαφορετική έκδοση του MS Word κατά τη φόρτωση του εγγράφου, διασφαλίζοντας τη συμβατότητα ακόμη και αν το σύστημα προορισμού έχει διαφορετική έκδοση MS Word.

#### Ε: Πώς ωφελεί την εφαρμογή C# η ρύθμιση της έκδοσης του MS Word;

Α: Η ρύθμιση της έκδοσης του MS Word διασφαλίζει ότι το έγγραφο υποβάλλεται σε επεξεργασία σύμφωνα με την προβλεπόμενη μορφοποίηση και τις δυνατότητες της συγκεκριμένης έκδοσης, παρέχοντας συνεπή έξοδο.

#### Ε: Το Aspose.Words περιορίζεται στον χειρισμό μόνο εγγράφων DOCX;

Α: Όχι, το Aspose.Words υποστηρίζει διάφορες μορφές εγγράφων, συμπεριλαμβανομένων των DOC, RTF, HTML, PDF και άλλων, καθιστώντας το ένα ευέλικτο εργαλείο για το χειρισμό διαφορετικών τύπων εγγράφων.