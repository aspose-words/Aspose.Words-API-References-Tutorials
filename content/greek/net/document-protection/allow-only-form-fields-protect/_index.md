---
title: Να επιτρέπεται μόνο η προστασία πεδίων φόρμας στο έγγραφο του Word
linktitle: Να επιτρέπεται μόνο η προστασία πεδίων φόρμας στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.Words για .NET για προστασία στο έγγραφο word και να επιτρέπεται μόνο η επεξεργασία των πεδίων φόρμας.
type: docs
weight: 10
url: /el/net/document-protection/allow-only-form-fields-protect/
---
Η προστασία εγγράφων είναι ένα βασικό χαρακτηριστικό κατά την επεξεργασία λέξεων με αρχεία εντός της εφαρμογής C#. Με τη βιβλιοθήκη Aspose.Words για .NET, μπορείτε εύκολα να προστατεύσετε τα έγγραφά σας και να επιτρέψετε μόνο την επεξεργασία πεδίων φόρμας. Σε αυτόν τον αναλυτικό οδηγό, θα σας καθοδηγήσουμε πώς να χρησιμοποιείτε τον πηγαίο κώδικα C# για να επιτρέπεται μόνο η επεξεργασία των πεδίων φόρμας χρησιμοποιώντας τη δυνατότητα Να επιτρέπεται μόνο προστασία πεδίων φόρμας του Aspose.Words για .NET.

## Βήμα 1: Ρύθμιση του καταλόγου εγγράφων

Το πρώτο βήμα είναι να ορίσετε τον κατάλογο του εγγράφου σας. Πρέπει να καθορίσετε τη διαδρομή στην οποία θέλετε να αποθηκεύσετε το προστατευμένο έγγραφο. Για παράδειγμα :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 2: Εισαγωγή ενοτήτων και κειμένου

Στη συνέχεια, πρέπει να εισαγάγετε ενότητες και κείμενο στο έγγραφό σας. Χρησιμοποιήστε την κλάση DocumentBuilder που παρέχεται από το Aspose.Words για να δημιουργήσετε το περιεχόμενο του εγγράφου σας. Εδώ είναι ένα απλό παράδειγμα:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Σε αυτό το παράδειγμα, δημιουργούμε ένα νέο κενό έγγραφο και, στη συνέχεια, χρησιμοποιούμε το DocumentBuilder για να προσθέσουμε μια γραμμή κειμένου.

## Βήμα 3: Ενεργοποίηση Προστασίας Εγγράφων

 Η προστασία εγγράφων λειτουργεί μόνο όταν είναι ενεργοποιημένη η προστασία εγγράφων. Μπορείτε να ενεργοποιήσετε την προστασία εγγράφων χρησιμοποιώντας το`Protect` μέθοδος της κλάσης Document. Δείτε πώς:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Σε αυτό το παράδειγμα, ενεργοποιούμε την προστασία εγγράφων καθορίζοντας τον τύπο προστασίας `

AllowOnlyFormFields` και ορισμός κωδικού πρόσβασης.

## Βήμα 4: Επιτρέποντας μόνο πεδία φόρμας

Τώρα που είναι ενεργοποιημένη η προστασία εγγράφων, πρέπει να καθορίσουμε ότι επιτρέπεται μόνο η επεξεργασία πεδίων φόρμας. Αυτό διασφαλίζει ότι οι χρήστες μπορούν να επεξεργάζονται μόνο τμήματα του εγγράφου που είναι πεδία φόρμας. Δείτε πώς:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Φροντίστε να αντικαταστήσετε τον "κωδικό πρόσβασης" με τον κωδικό πρόσβασης που ορίσατε νωρίτερα.

## Βήμα 5: Αποθήκευση του προστατευμένου εγγράφου

 Τέλος, μπορείτε να αποθηκεύσετε το προστατευμένο έγγραφο χρησιμοποιώντας το`Save` μέθοδος της κλάσης Document. Καθορίστε την πλήρη διαδρομή αρχείου και το επιθυμητό όνομα αρχείου. Για παράδειγμα :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Φροντίστε να αντικαταστήσετε το "dataDir" με τη διαδρομή προς τον κατάλογο εγγράφων σας.

### Παράδειγμα πηγαίου κώδικα για τη λειτουργία Allow Only Form Fields Protect χρησιμοποιώντας Aspose.Words για .NET

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Εισαγάγετε δύο ενότητες με κάποιο κείμενο.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Η προστασία εγγράφων λειτουργεί μόνο όταν η προστασία εγγράφων είναι ενεργοποιημένη και επιτρέπεται μόνο η επεξεργασία σε πεδία φόρμας.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Αποθηκεύστε το προστατευμένο έγγραφο.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## συμπέρασμα

Σε αυτόν τον οδηγό, εξερευνήσαμε τον τρόπο χρήσης της βιβλιοθήκης Aspose.Words για .NET για την προστασία ενός εγγράφου και για να επιτρέπεται μόνο η επεξεργασία πεδίων φόρμας. Ακολουθώντας τα βήματα που παρέχονται, μπορείτε εύκολα να εφαρμόσετε αυτήν τη λειτουργία στην εφαρμογή σας C#. Η προστασία των εγγράφων είναι απαραίτητη για τη διασφάλιση της ασφάλειας και της εμπιστευτικότητας των εγγράφων σας.

### Συχνές ερωτήσεις για τα πεδία φόρμας άδειας μόνο για προστασία στο έγγραφο του Word

#### Ε: Τι είναι η προστασία εγγράφων στο Aspose.Words για .NET;

Α: Προστασία εγγράφων στο Aspose.Words για .NET είναι μια δυνατότητα που σας επιτρέπει να ασφαλίζετε τα έγγραφά σας περιορίζοντας ορισμένες ενέργειες, όπως επεξεργασία, μορφοποίηση ή τροποποίηση περιεχομένου. Βοηθά στη διατήρηση της ακεραιότητας και της εμπιστευτικότητας των εγγράφων σας αποτρέποντας μη εξουσιοδοτημένες αλλαγές.

#### Ε: Πώς μπορώ να προστατεύσω ένα έγγραφο και να επιτρέψω την επεξεργασία μόνο πεδίων φόρμας χρησιμοποιώντας το Aspose.Words για .NET;

Α: Για να προστατεύσετε ένα έγγραφο και να επιτρέψετε την επεξεργασία μόνο πεδίων φόρμας χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να ακολουθήσετε τα εξής βήματα:
1. Καθορίστε τη διαδρομή καταλόγου για το έγγραφό σας.
2.  Εισαγάγετε ενότητες και κείμενο στο έγγραφό σας χρησιμοποιώντας το`DocumentBuilder` τάξη.
3.  Ενεργοποιήστε την προστασία εγγράφων χρησιμοποιώντας το`Protect` μέθοδος του`Document` κλάση, προσδιορίζοντας τον τύπο προστασίας ως`AllowOnlyFormFields` και παρέχοντας κωδικό πρόσβασης.
4.  Αποθηκεύστε το προστατευμένο έγγραφο χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

#### Ε: Μπορώ να εισαγάγω πεδία φόρμας σε ένα προστατευμένο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET;

Α: Ναι, μπορείτε να εισαγάγετε πεδία φόρμας σε ένα προστατευμένο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Η προστασία εγγράφων με το`AllowOnlyFormFields` Ο τύπος επιτρέπει στους χρήστες να επεξεργάζονται μόνο τα πεδία της φόρμας προστατεύοντας παράλληλα το υπόλοιπο περιεχόμενο του εγγράφου. Μπορείτε να χρησιμοποιήσετε το`DocumentBuilder` κλάση για να εισαγάγετε πεδία φόρμας στο έγγραφο πριν ενεργοποιήσετε την προστασία.

#### Ε: Μπορώ να αφαιρέσω την προστασία εγγράφων από ένα προστατευμένο έγγραφο;

 Α: Ναι, μπορείτε να καταργήσετε την προστασία εγγράφου από ένα προστατευμένο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Για να αφαιρέσετε την προστασία, μπορείτε να χρησιμοποιήσετε το`Unprotect` μέθοδος του`Document` τάξη και δώστε τον σωστό κωδικό πρόσβασης. Αυτό θα καταργήσει την προστασία και θα επιτρέψει την απεριόριστη επεξεργασία του εγγράφου.

#### Ε: Είναι δυνατή η προστασία ενός εγγράφου με πολλούς τύπους προστασίας;

 Α: Όχι, το Aspose.Words για .NET επιτρέπει την εφαρμογή μόνο ενός τύπου προστασίας σε ένα έγγραφο κάθε φορά. Ωστόσο, το`AllowOnlyFormFields` Ο τύπος προστασίας μπορεί να περιορίσει αποτελεσματικά την επεξεργασία σε πεδία σχηματισμού, ενώ επιτρέπει άλλους τύπους προστασίας, όπως π.χ`AllowOnlyComments` ή`AllowOnlyRevisions`να συνδυαστεί με προστασία πεδίου φόρμας.

#### Ε: Μπορώ να ορίσω διαφορετικούς κωδικούς πρόσβασης για διαφορετικούς τύπους προστασίας σε ένα έγγραφο;

Α: Όχι, το Aspose.Words για .NET σάς επιτρέπει να ορίσετε έναν μοναδικό κωδικό πρόσβασης για την προστασία εγγράφων, ανεξάρτητα από τον τύπο προστασίας. Ο ίδιος κωδικός πρόσβασης θα χρησιμοποιηθεί για την ενεργοποίηση και απενεργοποίηση της προστασίας εγγράφων.