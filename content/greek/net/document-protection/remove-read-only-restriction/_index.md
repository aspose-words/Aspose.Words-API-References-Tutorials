---
title: Καταργήστε τον περιορισμό μόνο για ανάγνωση
linktitle: Καταργήστε τον περιορισμό μόνο για ανάγνωση
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να καταργήσετε τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/document-protection/remove-read-only-restriction/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στα βήματα για να χρησιμοποιήσετε τη δυνατότητα αφαίρεσης περιορισμών Aspose.Words για .NET μόνο για ανάγνωση. Αυτή η δυνατότητα σάς επιτρέπει να καταργήσετε τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word για να το κάνετε επεξεργάσιμο. Ακολουθήστε τα παρακάτω βήματα:

## Βήμα 1: Δημιουργία του εγγράφου και ρύθμιση της προστασίας

Ξεκινήστε δημιουργώντας μια παρουσία της κλάσης Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Ορίστε έναν κωδικό πρόσβασης για το έγγραφο χρησιμοποιώντας την ιδιότητα SetPassword() του αντικειμένου WriteProtection:

Φροντίστε να αντικαταστήσετε το "MyPassword" με τον πραγματικό κωδικό πρόσβασης που χρησιμοποιήσατε για την προστασία του εγγράφου.

## Βήμα 2: Καταργήστε τον περιορισμό μόνο για ανάγνωση

Για να καταργήσετε τον περιορισμό μόνο για ανάγνωση, ορίστε την ιδιότητα ReadOnlyRecommended σε false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Βήμα 3: Εφαρμόστε απεριόριστη προστασία

Τέλος, εφαρμόστε απεριόριστη προστασία χρησιμοποιώντας τη μέθοδο Protect() του αντικειμένου Document:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και όνομα αρχείου για να αποθηκεύσετε το έγγραφο χωρίς τον περιορισμό μόνο για ανάγνωση.

### Παράδειγμα πηγαίου κώδικα για Κατάργηση περιορισμού μόνο για ανάγνωση χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για την κατάργηση του περιορισμού μόνο για ανάγνωση χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Εισαγάγετε έναν κωδικό πρόσβασης με μήκος έως 15 χαρακτήρες.
doc.WriteProtection.SetPassword("MyPassword");

//Καταργήστε την επιλογή μόνο για ανάγνωση.
doc.WriteProtection.ReadOnlyRecommended = false;

// Εφαρμόστε προστασία εγγραφής χωρίς καμία προστασία.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να καταργήσετε τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word με το Aspose.Words για .NET.


## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να καταργήσουμε τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τα βήματα που παρέχονται, μπορείτε εύκολα να καταργήσετε τον περιορισμό και να κάνετε ξανά το έγγραφο επεξεργάσιμο. Το Aspose.Words για .NET προσφέρει ένα ολοκληρωμένο σύνολο δυνατοτήτων για τη διαχείριση της προστασίας και των περιορισμών εγγράφων, παρέχοντάς σας ευελιξία και έλεγχο της ασφάλειας και των δυνατοτήτων επεξεργασίας των εγγράφων του Word.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο περιορισμός μόνο για ανάγνωση στο Aspose.Words για .NET;

Α: Ο περιορισμός μόνο για ανάγνωση στο Aspose.Words για .NET αναφέρεται σε μια δυνατότητα που σας επιτρέπει να ορίσετε ένα έγγραφο του Word ως μόνο για ανάγνωση, εμποδίζοντας τους χρήστες να κάνουν τροποποιήσεις στο περιεχόμενο ή τη μορφοποίηση. Αυτός ο περιορισμός συμβάλλει στην προστασία της ακεραιότητας του εγγράφου και διασφαλίζει ότι δεν τροποποιείται κατά λάθος ή κακόβουλα.

#### Ε: Πώς μπορώ να καταργήσω τον περιορισμό μόνο για ανάγνωση χρησιμοποιώντας το Aspose.Words για .NET;

Α: Για να καταργήσετε τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να ακολουθήσετε τα εξής βήματα:
1.  Δημιουργήστε ένα παράδειγμα του`Document` τάξη και ορίστε έναν κωδικό πρόσβασης για το έγγραφο χρησιμοποιώντας το`SetPassword` μέθοδος του`WriteProtection` αντικείμενο.
2.  Ρυθμίστε το`ReadOnlyRecommended` ιδιοκτησία του`WriteProtection` αντιτίθεμαι`false` για να καταργήσετε τη σύσταση μόνο για ανάγνωση.
3.  Εφαρμόστε απεριόριστη προστασία στο έγγραφο χρησιμοποιώντας το`Protect` μέθοδος του`Document` αντικείμενο με το`NoProtection` τύπος προστασίας.
4.  Αποθηκεύστε το έγγραφο χωρίς τον περιορισμό μόνο για ανάγνωση χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

#### Ε: Μπορώ να καταργήσω τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word χωρίς κωδικό πρόσβασης;

Α: Όχι, δεν μπορείτε να καταργήσετε τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word χωρίς να παρέχετε τον σωστό κωδικό πρόσβασης. Ο περιορισμός μόνο για ανάγνωση έχει οριστεί για λόγους ασφαλείας και η κατάργησή του χωρίς τον κωδικό πρόσβασης θα υπονόμευε τον σκοπό προστασίας της ακεραιότητας του εγγράφου.

#### Ε: Μπορώ να καταργήσω τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word με λάθος κωδικό πρόσβασης;

Α: Όχι, δεν μπορείτε να καταργήσετε τον περιορισμό μόνο για ανάγνωση από ένα έγγραφο του Word με λάθος κωδικό πρόσβασης. Πρέπει να παρέχεται ο σωστός κωδικός πρόσβασης για να καταργηθεί ο περιορισμός μόνο για ανάγνωση και να γίνει ξανά επεξεργάσιμο το έγγραφο. Αυτό διασφαλίζει ότι μόνο εξουσιοδοτημένοι χρήστες με τον σωστό κωδικό πρόσβασης μπορούν να τροποποιήσουν το έγγραφο.

#### Ε: Είναι δυνατή η κατάργηση άλλων τύπων προστασίας εγγράφων χρησιμοποιώντας το Aspose.Words για .NET;

Α: Ναι, το Aspose.Words για .NET παρέχει διάφορες μεθόδους για την κατάργηση άλλων τύπων προστασίας εγγράφων, όπως προστασία με κωδικό πρόσβασης, προστασία φόρμας ή περιορισμούς επεξεργασίας εγγράφων. Ανάλογα με τον τύπο προστασίας που εφαρμόζεται στο έγγραφο, μπορείτε να χρησιμοποιήσετε τις αντίστοιχες μεθόδους και ιδιότητες που παρέχονται από το Aspose.Words για να καταργήσετε τη συγκεκριμένη προστασία και να κάνετε το έγγραφο επεξεργάσιμο.