---
title: Εισαγωγή πεδίου χρησιμοποιώντας το εργαλείο δημιουργίας πεδίων
linktitle: Εισαγωγή πεδίου χρησιμοποιώντας το εργαλείο δημιουργίας πεδίων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισάγετε προσαρμοσμένα πεδία στα έγγραφά σας στο Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fields/insert-field-using-field-builder/
---

Ακολουθεί ένας αναλυτικός οδηγός για να εξηγήσετε τον πηγαίο κώδικα C# παρακάτω, ο οποίος χρησιμοποιεί τη δυνατότητα "Εισαγωγή πεδίου χρησιμοποιώντας το FieldBuilder" του Aspose.Words για .NET. Φροντίστε να ακολουθήσετε προσεκτικά κάθε βήμα για να έχετε τα επιθυμητά αποτελέσματα.

## Βήμα 1: Ρύθμιση καταλόγου εγγράφων

Στον κωδικό που παρέχεται, πρέπει να καθορίσετε τον κατάλογο των εγγράφων σας. Αντικαταστήστε την τιμή "YOUR DOCUMENT DIRECTORY" με την κατάλληλη διαδρομή προς τον κατάλογο των εγγράφων σας.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργία του εγγράφου

Ξεκινάμε δημιουργώντας ένα νέο έγγραφο.

```csharp
Document doc = new Document();
```

## Βήμα 3: Δημιουργία του πεδίου IF χρησιμοποιώντας το FieldBuilder

Χρησιμοποιούμε την κλάση FieldBuilder για να κατασκευάσουμε ένα πεδίο IF με δύο ένθετα πεδία MERGEFIELD. Σε αυτό το παράδειγμα, το πεδίο IF εμφανίζει το όνομα και το επώνυμο με βάση μια συνθήκη.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Βήμα 4: Εισαγωγή του πεδίου IF στο έγγραφο

 Χρησιμοποιούμε το`BuildAndInsert()` μέθοδο δημιουργίας και εισαγωγής του πεδίου IF σε μια συγκεκριμένη θέση στο έγγραφο.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Παράδειγμα πηγαίου κώδικα για την εισαγωγή ενός πεδίου χρησιμοποιώντας το FieldBuilder με Aspose.Words για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργία εγγράφου.
Document doc = new Document();

// Κατασκευή του πεδίου IF χρησιμοποιώντας το FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Εισαγάγετε το πεδίο IF στο έγγραφο.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

Σε αυτό το παράδειγμα, δημιουργήσαμε ένα νέο έγγραφο, δημιουργήσαμε ένα πεδίο IF με ένθετα πεδία MERGEFIELD και, στη συνέχεια, εισαγάγαμε αυτό το πεδίο στο έγγραφο σε μια καθορισμένη θέση. Στη συνέχεια, το έγγραφο αποθηκεύεται με ένα συγκεκριμένο όνομα αρχείου.

### Συχνές ερωτήσεις

#### Ε: Τι είναι ο κατασκευαστής πεδίου στο Aspose.Words;

A: Ένα Field Builder στο Aspose.Words είναι ένα ισχυρό εργαλείο για τη δημιουργία και τον χειρισμό πεδίων σε ένα έγγραφο του Word. Προσφέρει προηγμένες δυνατότητες για τη δημιουργία και την προσαρμογή πεδίων, συμπεριλαμβανομένης της εισαγωγής κωδικών πεδίων και της διαχείρισης επιλογών μορφοποίησης.

#### Ε: Τι τύποι πεδίων μπορούν να εισαχθούν χρησιμοποιώντας το εργαλείο δημιουργίας πεδίων;

Α: Το εργαλείο δημιουργίας πεδίων στο Aspose.Words σάς επιτρέπει να εισάγετε διαφορετικούς τύπους πεδίων σε ένα έγγραφο του Word. Ακολουθούν μερικά παραδείγματα τύπων πεδίων που χρησιμοποιούνται συνήθως:

- MERGEFIELD: χρησιμοποιείται για τη συγχώνευση δεδομένων από εξωτερικές πηγές.
- DATE: εμφανίζει την τρέχουσα ημερομηνία.
- PAGE: εμφανίζει τον τρέχοντα αριθμό σελίδας.
- IF: επιτρέπει τη ρύθμιση της εμφάνισης ενός περιεχομένου σύμφωνα με μια συνθήκη.
- TOC: δημιουργεί αυτόματα έναν πίνακα περιεχομένων με βάση τα στυλ τίτλου του εγγράφου.

#### Ε: Πώς να προσαρμόσετε τα πεδία που έχουν εισαχθεί με το εργαλείο δημιουργίας πεδίων;

Α: Το εργαλείο δημιουργίας πεδίων προσφέρει επιλογές προσαρμογής για πεδία που έχουν εισαχθεί. Μπορείτε να χρησιμοποιήσετε μεθόδους και ιδιότητες κατασκευής πεδίων για να ορίσετε επιλογές όπως μορφοποίηση πεδίων, ορίσματα, διακόπτες και προεπιλεγμένες τιμές. Για παράδειγμα, μπορείτε να ορίσετε τη μορφή ημερομηνίας, τη μορφή αριθμού, το διαχωριστικό χιλιάδων κ.λπ.
  