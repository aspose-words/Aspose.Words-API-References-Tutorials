---
title: Οριζόντια μορφή κανόνα σε έγγραφο Word
linktitle: Οριζόντια μορφή κανόνα σε έγγραφο Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να μορφοποιείτε οριζόντιους κανόνες σε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET. Οδηγός βήμα προς βήμα.
type: docs
weight: 10
url: /el/net/add-content-using-documentbuilder/horizontal-rule-format/
---
Σε αυτό το ολοκληρωμένο παράδειγμα, θα μάθετε πώς να μορφοποιείτε έναν οριζόντιο κανόνα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας καθοδηγήσουμε στη διαδικασία και θα σας παρέχουμε τα απαραίτητα αποσπάσματα κώδικα C#. Μέχρι το τέλος αυτού του οδηγού, θα μπορείτε να προσαρμόσετε τη στοίχιση, το πλάτος, το ύψος, το χρώμα και άλλες ιδιότητες ενός οριζόντιου κανόνα.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Η βιβλιοθήκη Aspose.Words for .NET είναι εγκατεστημένη στο σύστημά σας.

## Βήμα 1: Δημιουργήστε ένα DocumentBuilder και εισαγάγετε έναν οριζόντιο κανόνα
Για να ξεκινήσετε, δημιουργήστε ένα αντικείμενο DocumentBuilder και χρησιμοποιήστε τη μέθοδο InsertHorizontalRule για να εισαγάγετε έναν οριζόντιο κανόνα:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Βήμα 2: Πρόσβαση στη Μορφή Οριζόντιας Κανόνας
Στη συνέχεια, αποκτήστε πρόσβαση στην ιδιότητα HorizontalRuleFormat του αντικειμένου Shape για να ανακτήσετε τις επιλογές μορφοποίησης:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Βήμα 3: Προσαρμόστε τις Επιλογές Μορφοποίησης
Τώρα, μπορείτε να προσαρμόσετε διάφορες επιλογές μορφοποίησης για τον οριζόντιο κανόνα. Για παράδειγμα, μπορείτε να προσαρμόσετε τη στοίχιση, το πλάτος, το ύψος, το χρώμα και τη σκίαση:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
Μετά τη μορφοποίηση του οριζόντιου κανόνα, αποθηκεύστε το έγγραφο σε ένα αρχείο χρησιμοποιώντας τη μέθοδο Save του αντικειμένου Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Παράδειγμα πηγαίου κώδικα για οριζόντια μορφή κανόνα χρησιμοποιώντας Aspose.Words για .NET
Ακολουθεί ο πλήρης πηγαίος κώδικας για τη μορφοποίηση ενός οριζόντιου κανόνα χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Θυμηθείτε να προσαρμόσετε τον κώδικα σύμφωνα με τις συγκεκριμένες απαιτήσεις σας και να τον βελτιώσετε με πρόσθετη λειτουργικότητα όπως απαιτείται.

## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να μορφοποιείτε έναν οριζόντιο κανόνα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα, μπορείτε τώρα να προσαρμόσετε την εμφάνιση οριζόντιων κανόνων για να βελτιώσετε την οπτική διάταξη του εγγράφου σας.

Πειραματιστείτε με διαφορετικές επιλογές μορφοποίησης για να επιτύχετε το επιθυμητό στυλ και εφέ για τους οριζόντιους κανόνες σας.

### Συχνές ερωτήσεις για τη μορφή οριζόντιων κανόνων στο έγγραφο του Word

#### Ε: Μπορώ να εφαρμόσω διαφορετικά χρώματα στον οριζόντιο κανόνα;

Α: Απολύτως! Με το Aspose.Words για .NET, μπορείτε εύκολα να προσαρμόσετε το χρώμα του οριζόντιου κανόνα ορίζοντας την ιδιότητα Color στην επιθυμητή τιμή χρώματος. Αυτό σας επιτρέπει να αντιστοιχίσετε τον οριζόντιο κανόνα με τη συνολική σχεδίαση του εγγράφου σας.

#### Ε: Είναι δυνατή η προσαρμογή του πλάτους και του ύψους του οριζόντιου κανόνα;

Α: Ναι, έχετε τον πλήρη έλεγχο του πλάτους και του ύψους του οριζόντιου κανόνα. Τροποποιώντας τις ιδιότητες WidthPercent και Height, μπορείτε να επιτύχετε τις επιθυμητές διαστάσεις για τον οριζόντιο κανόνα.

#### Ε: Μπορώ να αλλάξω τη στοίχιση του οριζόντιου κανόνα μέσα στο έγγραφο;

Α: Σίγουρα! Το Aspose.Words για .NET σάς δίνει τη δυνατότητα να καθορίσετε την στοίχιση του οριζόντιου κανόνα χρησιμοποιώντας την ιδιότητα Alignment. Μπορείτε να επιλέξετε από διάφορες επιλογές όπως Κέντρο, Αριστερά, Δεξιά και Δικαιολογημένα.

#### Ε: Μπορώ να εφαρμόσω σκίαση ή χρώμα φόντου στον οριζόντιο κανόνα;

Α: Ναι, μπορείτε να προσθέσετε σκίαση ή χρώμα φόντου στον οριζόντιο κανόνα. Από προεπιλογή, η ιδιότητα NoShade έχει οριστεί σε true, αλλά μπορείτε να την ορίσετε σε false και να ορίσετε τη σκίαση χρησιμοποιώντας τις κατάλληλες μεθόδους.

#### Ε: Μπορώ να εισαγάγω πολλούς οριζόντιους κανόνες σε ένα μόνο έγγραφο;

Α: Απολύτως! Μπορείτε να εισαγάγετε πολλούς οριζόντιους κανόνες σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Απλώς επαναλάβετε τα βήματα στο σεμινάριο όσο χρειάζεται για να προσθέσετε όσους οριζόντιους κανόνες θέλετε.