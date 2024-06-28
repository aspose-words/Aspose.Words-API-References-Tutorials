---
title: Εισαγωγή πεδίου Συμπερίληψη κειμένου χωρίς Εργαλείο δημιουργίας εγγράφων
linktitle: Εισαγωγή FieldIncludeText Χωρίς Εργαλείο δημιουργίας εγγράφων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισαγάγετε ένα πεδίο FieldIncludeText στα έγγραφα του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Ακολουθεί ένας αναλυτικός οδηγός για να εξηγήσετε τον πηγαίο κώδικα C# παρακάτω, ο οποίος χρησιμοποιεί τη λειτουργικότητα "Εισαγωγή πεδίου FieldIncludeText" του Aspose.Words για .NET. Φροντίστε να ακολουθήσετε προσεκτικά κάθε βήμα για να έχετε τα επιθυμητά αποτελέσματα.

## Βήμα 1: Ρύθμιση καταλόγου εγγράφων

Στον κωδικό που παρέχεται, πρέπει να καθορίσετε τον κατάλογο των εγγράφων σας. Αντικαταστήστε την τιμή "YOUR DOCUMENT DIRECTORY" με την κατάλληλη διαδρομή προς τον κατάλογο των εγγράφων σας.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργία του εγγράφου και της παραγράφου

Ξεκινάμε δημιουργώντας ένα νέο έγγραφο και αρχικοποιώντας μια παράγραφο.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Βήμα 3: Εισαγωγή του πεδίου FieldIncludeText

 Χρησιμοποιούμε το`AppendField()` μέθοδος για την εισαγωγή ενός πεδίου FieldIncludeText στην παράγραφο.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Στη συνέχεια, διαμορφώνουμε τις ιδιότητες του πεδίου FieldIncludeText, καθορίζοντας το όνομα του σελιδοδείκτη και το όνομα του αρχείου προέλευσης.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Στη συνέχεια, προσθέτουμε την παράγραφο στο σώμα του εγγράφου.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Τέλος, ονομάζουμε το`Update()` μέθοδο ενημέρωσης του πεδίου.

```csharp
fieldIncludeText.Update();
```

### Παράδειγμα του πηγαίου κώδικα για την εισαγωγή ενός πεδίου FieldIncludeText με Aspose.Words για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργήστε το έγγραφο και την παράγραφο.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Εισαγωγή πεδίου FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

Σε αυτό το παράδειγμα, δημιουργήσαμε ένα νέο έγγραφο, αρχικοποιήσαμε μια παράγραφο, εισαγάγαμε ένα FieldIncludeTexten προσδιορίζοντας το όνομα του σελιδοδείκτη και το όνομα του αρχείου προέλευσης και αποθηκεύσαμε το έγγραφο με ένα καθορισμένο όνομα αρχείου.

Αυτό ολοκληρώνει τον οδηγό μας σχετικά με τη χρήση της δυνατότητας "Εισαγωγή FieldIncludeText" με το Aspose.Words για .NET.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να καθορίσω το αρχείο προέλευσης για το πεδίο συμπερίληψης κειμένου στο Aspose.Words για .NET;

 Α: Για να καθορίσετε το αρχείο προέλευσης για το πεδίο συμπερίληψης κειμένου στο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`FieldIncludeText.SourceFullName`ιδιότητα για να ορίσετε την πλήρη διαδρομή του αρχείου προέλευσης. Βεβαιωθείτε ότι το αρχείο προέλευσης είναι προσβάσιμο και περιέχει το περιεχόμενο που θέλετε να συμπεριλάβετε στο πεδίο συμπερίληψης κειμένου.

#### Ε: Μπορώ να συμπεριλάβω κείμενο από μια μακροεντολή στο πεδίο συμπερίληψης κειμένου με το Aspose.Words για .NET;

 Α: Ναι, μπορείτε να συμπεριλάβετε κείμενο από μια μακροεντολή στο πεδίο συμπερίληψης κειμένου με το Aspose.Words για .NET. Μπορείτε να χρησιμοποιήσετε το`FieldIncludeText.IncludeText` ιδιότητα για να καθορίσετε το όνομα της μακροεντολής της οποίας το περιεχόμενο πρέπει να συμπεριληφθεί στο πεδίο.

#### Ε: Η εισαγωγή κειμένου περιλαμβάνει πεδίο χωρίς το εργαλείο δημιουργίας εγγράφων επηρεάζει τη δομή του εγγράφου του Word με το Aspose.Words για .NET;

Α: Η εισαγωγή ενός πεδίου συμπερίληψης κειμένου χωρίς το εργαλείο δημιουργίας εγγράφων δεν επηρεάζει άμεσα τη δομή του εγγράφου του Word. Ωστόσο, προσθέτει ένα νέο στοιχείο πεδίου στο περιεχόμενο του εγγράφου. Μπορείτε να χειριστείτε τη δομή του εγγράφου προσθέτοντας, διαγράφοντας ή τροποποιώντας τα υπάρχοντα στοιχεία σύμφωνα με τις ανάγκες σας.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του πεδίου συμπερίληψης κειμένου σε ένα έγγραφο του Word με το Aspose.Words για .NET;

Α: Η συμπερίληψη πεδίου κειμένου δεν προσαρμόζει απευθείας την εμφάνισή του σε ένα έγγραφο του Word. Ωστόσο, μπορείτε να μορφοποιήσετε το κείμενο που περιλαμβάνεται χρησιμοποιώντας τις ιδιότητες παραγράφου, τις ιδιότητες γραμματοσειράς και άλλα αντικείμενα μορφοποίησης που είναι διαθέσιμα στο Aspose.Words για .NET.