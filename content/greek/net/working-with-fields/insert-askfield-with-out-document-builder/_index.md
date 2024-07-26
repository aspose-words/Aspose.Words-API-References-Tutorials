---
title: Εισαγάγετε το ASKField χωρίς Εργαλείο δημιουργίας εγγράφων
linktitle: Εισαγάγετε το ASKField χωρίς Εργαλείο δημιουργίας εγγράφων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισάγετε ένα πεδίο ASK στα έγγραφά σας στο Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Ακολουθεί ένας οδηγός βήμα προς βήμα για να εξηγήσετε τον πηγαίο κώδικα C# παρακάτω, ο οποίος χρησιμοποιεί τη δυνατότητα "Εισαγωγή πεδίου ASK χωρίς DocumentBuilder" του Aspose.Words για .NET. Φροντίστε να ακολουθήσετε προσεκτικά κάθε βήμα για να έχετε τα επιθυμητά αποτελέσματα.

## Βήμα 1: Ρύθμιση καταλόγου εγγράφων

Στον κωδικό που παρέχεται, πρέπει να καθορίσετε τον κατάλογο των εγγράφων σας. Αντικαταστήστε την τιμή "YOUR DOCUMENT DIRECTORY" με την κατάλληλη διαδρομή προς τον κατάλογο των εγγράφων σας.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργία του εγγράφου και της παραγράφου

Ξεκινάμε δημιουργώντας ένα νέο έγγραφο και ανακτώντας την πρώτη παράγραφο.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Βήμα 3: Εισαγωγή του πεδίου ASK

 Χρησιμοποιούμε το`AppendField()` μέθοδο για την εισαγωγή ενός πεδίου ASK στην παράγραφο.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Στη συνέχεια διαμορφώνουμε τις διάφορες ιδιότητες του πεδίου ASK καθορίζοντας τις επιθυμητές τιμές.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Τέλος, ονομάζουμε το`Update()` μέθοδο ενημέρωσης του πεδίου.

```csharp
field. Update();
```

### Παράδειγμα πηγαίου κώδικα για την εισαγωγή πεδίου ASK χωρίς DocumentBuilder με Aspose.Words για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργία εγγράφου.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Εισαγάγετε το πεδίο ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Σε αυτό το παράδειγμα, δημιουργήσαμε ένα νέο έγγραφο, εισαγάγαμε ένα πεδίο ASK χωρίς να χρησιμοποιήσουμε το DocumentBuilder, διαμορφώσαμε τις διάφορες ιδιότητες του πεδίου και αποθηκεύσαμε το έγγραφο με ένα καθορισμένο όνομα αρχείου.

Αυτό ολοκληρώνει τον οδηγό μας σχετικά με τη χρήση της δυνατότητας "Εισαγωγή πεδίου ASK χωρίς DocumentBuilder" με το Aspose.Words για .NET.

### Συχνές ερωτήσεις

#### Ε: Τι είναι ένα πεδίο ASK στο Aspose.Words;

Α: Ένα πεδίο ASK στο Aspose.Words χρησιμοποιείται για να υποβάλει στον χρήστη μια ερώτηση κατά το άνοιγμα ενός εγγράφου. Συχνά χρησιμοποιείται για να ζητήσει συγκεκριμένες πληροφορίες ή σχόλια που μπορεί να διαφέρουν από χρήστη σε χρήστη.

#### Ε: Πώς να εισαγάγετε το πεδίο ASK στο έγγραφο του Word χωρίς να χρησιμοποιήσετε το Document Builder στο Aspose.Words;

Α: Για να εισαγάγετε ένα πεδίο ASK σε ένα έγγραφο του Word χωρίς να χρησιμοποιήσετε το Document Builder στο Aspose.Words, μπορείτε να ακολουθήσετε τα εξής βήματα:

1. Εισαγωγή Document και Field class από τον χώρο ονομάτων Aspose.Words.Fields.
2. Δημιουργήστε μια παρουσία εγγράφου φορτώνοντας το υπάρχον έγγραφό σας.
3. Χρησιμοποιήστε τη μέθοδο InsertField για να εισαγάγετε ένα πεδίο ASK καθορίζοντας το όνομα της ερώτησης.
4. Αποθηκεύστε το έγγραφο.

#### Ε: Πώς μπορώ να λάβω την απάντηση χρήστη για ένα πεδίο ASK σε ένα έγγραφο του Word;

Α: Για να λάβετε την απάντηση του χρήστη για ένα πεδίο ASK σε ένα έγγραφο του Word, μπορείτε να χρησιμοποιήσετε τη μέθοδο GetFieldNames που είναι διαθέσιμη στην κλάση Document. Αυτή η μέθοδος επιστρέφει μια λίστα με τα ονόματα των πεδίων που υπάρχουν στο έγγραφο. Στη συνέχεια, μπορείτε να ελέγξετε εάν το όνομα του πεδίου ASK υπάρχει στη λίστα και να ανακτήσετε τη σχετική απάντηση.

#### Ε: Μπορεί το πεδίο ASK να χρησιμοποιηθεί για να ζητηθούν περισσότερες πληροφορίες από τον χρήστη;

Α: Ναι, το πεδίο ASK μπορεί να χρησιμοποιηθεί για να ζητηθούν πολλές πληροφορίες από τον χρήστη. Μπορείτε να εισαγάγετε πολλά πεδία ASK στο έγγραφό σας, το καθένα με διαφορετική ερώτηση. Όταν ανοίξει το έγγραφο, ο χρήστης θα κληθεί για τις αντίστοιχες απαντήσεις.