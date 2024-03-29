---
title: Συλλαβισμός Επιστροφή κλήσης
linktitle: Συλλαβισμός Επιστροφή κλήσης
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε την επιστροφή κλήσης με συλλαβισμό στο Aspose.Words για .NET για να χειρίζεστε τον συλλαβισμό λέξεων.
type: docs
weight: 10
url: /el/net/working-with-hyphenation/hyphenation-callback/
---

Σε αυτό το βήμα προς βήμα εκμάθηση, θα σας δείξουμε πώς να χρησιμοποιήσετε τη δυνατότητα επανάκλησης συλλαβισμού στο Aspose.Words για .NET. Θα εξηγήσουμε τον παρεχόμενο πηγαίο κώδικα C# και θα σας δείξουμε πώς να τον εφαρμόσετε στα δικά σας έργα.

 Για να ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει το Aspose.Words για .NET στο περιβάλλον ανάπτυξης σας. Εάν δεν το έχετε κάνει ήδη, κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από[Aspose.Releases]https://releases.aspose.com/words/net/.

## Βήμα 1: Αποθήκευση υπενθύμισης συλλαβισμού

 Αρχικά, θα καταχωρήσουμε τον συλλαβισμό επανάκλησης χρησιμοποιώντας ένα προσαρμοσμένο`CustomHyphenationCallback` τάξη. Αυτό θα μας επιτρέψει να χειριστούμε τον παύλα των λέξεων σύμφωνα με τους δικούς μας κανόνες:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Βεβαιωθείτε ότι έχετε εφαρμόσει το`CustomHyphenationCallback` τάξη σύμφωνα με τις ιδιαίτερες ανάγκες σας.

## Βήμα 2: Φόρτωση του εγγράφου και εφαρμογή παύλασης

Στη συνέχεια, φορτώστε το έγγραφό σας από τον καθορισμένο κατάλογο και πληκτρολογήστε τις λέξεις χρησιμοποιώντας το Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Βήμα 3: Χειρισμός σφαλμάτων λεξικού που λείπουν

Σε περίπτωση που λείπει ένα λεξικό συλλαβισμού, θα συλλάβουμε την αντίστοιχη εξαίρεση και θα εμφανίσουμε ένα μήνυμα σφάλματος:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Βήμα 4: Εκκαθάριση και απενεργοποίηση υπενθύμισης συλλαβισμού

Τέλος, για καθαριότητα και για να απενεργοποιήσετε την υπενθύμιση συλλαβισμού, ακολουθήστε τα παρακάτω βήματα:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Αυτό καθαρίζει και απενεργοποιεί την υπενθύμιση συλλαβισμού μετά την ολοκλήρωση της επεξεργασίας.

Ετσι ! Χρησιμοποιήσατε επιτυχώς την επιστροφή κλήσης συλλαβισμού στο Aspose.Words για .NET.

### Δείγμα πηγαίου κώδικα για επιστροφή κλήσης συλλαβισμού με Aspose.Words για .NET

```csharp
try
{
	 // Καταχωρίστε την επιστροφή κλήσης με συλλαβισμό.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Μη διστάσετε να χρησιμοποιήσετε αυτόν τον κώδικα στα δικά σας έργα και να τον τροποποιήσετε ώστε να ταιριάζει στις συγκεκριμένες ανάγκες σας.

### Συχνές ερωτήσεις

#### Ε: Τι είναι η υπενθύμιση συλλαβών στο Aspose.Words;

A: Μια υπενθύμιση συλλαβοποίησης στο Aspose.Words είναι μια δυνατότητα που σας επιτρέπει να προσαρμόσετε τον τρόπο συλλαβοποίησης των λέξεων στα έγγραφά σας. Χρησιμοποιώντας μια υπενθύμιση συλλαβής, μπορείτε να καθορίσετε προσαρμοσμένους κανόνες για τη συλλαβή των λέξεων, οι οποίοι μπορεί να είναι χρήσιμοι για συγκεκριμένες γλώσσες ή συγκεκριμένα σενάρια όπου η προεπιλεγμένη συλλαβή δεν παράγει τα επιθυμητά αποτελέσματα.

#### Ε: Πώς να ορίσετε μια υπενθύμιση συλλαβών στο Aspose.Words;

 Α: Για να ορίσετε μια επιστροφή κλήσης συλλαβισμού στο Aspose.Words, πρέπει να δημιουργήσετε μια κλάση που να υλοποιεί το`HyphenationCallback` διασύνδεση και υλοποίηση της`HandleWord()` μέθοδος. Αυτή η μέθοδος θα καλείται για κάθε λέξη που συναντάται κατά τη συλλαβή. Μπορείτε να εφαρμόσετε προσαρμοσμένους κανόνες συλλαβοποίησης σε αυτό και να επιστρέψετε τη συλλαβοποιημένη λέξη. Στη συνέχεια, μπορείτε να συνδέσετε τον συλλαβισμό επανάκλησης χρησιμοποιώντας το`Document.HyphenationCallback` ιδιοκτησία του εγγράφου σας.

#### Ε: Ποιο είναι το πλεονέκτημα της χρήσης υπενθύμισης συλλαβών στο Aspose.Words;

Α: Το πλεονέκτημα της χρήσης υπενθύμισης συλλαβοποίησης στο Aspose.Words είναι η δυνατότητα προσαρμογής του τρόπου με τον οποίο συλλαβίζονται οι λέξεις στα έγγραφά σας. Αυτό σας δίνει περισσότερο έλεγχο στη συλλαβή, ειδικά για συγκεκριμένες γλώσσες ή σενάρια όπου η προεπιλεγμένη συλλαβή δεν δίνει τα επιθυμητά αποτελέσματα. Μπορείτε να εφαρμόσετε συγκεκριμένους κανόνες σε κάθε λέξη για να αποκτήσετε ακριβή συλλαβή σύμφωνα με τις ανάγκες σας.

#### Ε: Ποια είναι μερικά κοινά σενάρια όπου η χρήση υπενθύμισης συλλαβών μπορεί να είναι χρήσιμη;

Α: Η χρήση ενός ενισχυτή συλλαβών μπορεί να είναι χρήσιμη σε πολλά σενάρια, όπως:
- Συλλαβοποίηση λέξεων σε συγκεκριμένες γλώσσες που έχουν συγκεκριμένους κανόνες συλλαβοποίησης.
- Η εφαρμογή εξατομικευμένων κανόνων συλλαβής για ακρωνύμια ή τεχνικές λέξεις.
- Προσαρμογή της συλλαβής σύμφωνα με υφολογικές προτιμήσεις ή τυπογραφικά πρότυπα.

#### Ε: Πώς μπορώ να δοκιμάσω προσαρμοσμένη συλλαβή με υπενθύμιση συλλαβών στο Aspose.Words;

 Α: Για να ελέγξετε την προσαρμοσμένη συλλαβή με μια υπενθύμιση συλλαβής στο Aspose.Words, μπορείτε να δημιουργήσετε ένα δοκιμαστικό έγγραφο που περιέχει λέξεις για τις οποίες θέλετε να εφαρμόσετε προσαρμοσμένους κανόνες συλλαβοποίησης. Στη συνέχεια, μπορείτε να ορίσετε την επιστροφή κλήσης της προσαρμοσμένης συλλαβής, καλέστε το`Document.Range.Replace()` μέθοδο για να αντικαταστήσετε τις λέξεις στο έγγραφο και χρησιμοποιήστε το`Hyphenate()` μέθοδος του`Hyphenation` τάξη για να πάρει τη συλλαβή των λέξεων . Στη συνέχεια, μπορείτε να μορφοποιήσετε τις συλλαβισμένες λέξεις όπως απαιτείται, για παράδειγμα προσθέτοντας παύλες μεταξύ των συλλαβών.