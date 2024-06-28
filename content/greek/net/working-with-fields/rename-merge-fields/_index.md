---
title: Μετονομασία πεδίων συγχώνευσης
linktitle: Μετονομασία πεδίων συγχώνευσης
second_title: Aspose.Words Document Processing API
description: Σε αυτό το σεμινάριο, θα μάθετε πώς να μετονομάζετε πεδία συγχώνευσης σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fields/rename-merge-fields/
---

Ακολουθεί ένας οδηγός βήμα προς βήμα για να εξηγήσετε τον πηγαίο κώδικα C# παρακάτω, ο οποίος χρησιμοποιεί τη δυνατότητα μετονομασίας πεδίων συγχώνευσης του Aspose.Words για .NET. Ακολουθήστε κάθε βήμα προσεκτικά για να έχετε τα επιθυμητά αποτελέσματα.

## Βήμα 1: Ρύθμιση καταλόγου εγγράφων

Στον κωδικό που παρέχεται, πρέπει να καθορίσετε τον κατάλογο των εγγράφων σας. Αντικαταστήστε την τιμή "YOUR DOCUMENT DIRECTORY" με την κατάλληλη διαδρομή προς τον κατάλογο των εγγράφων σας.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργία του εγγράφου και εισαγωγή των πεδίων συγχώνευσης

Ξεκινάμε δημιουργώντας ένα νέο έγγραφο και χρησιμοποιώντας ένα`DocumentBuilder` για να εισαγάγετε τα πεδία συγχώνευσης.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Βήμα 3: Μετονομασία πεδίων συγχώνευσης

Κάνουμε βρόχο σε κάθε πεδίο στην περιοχή εγγράφων και αν είναι πεδίο συγχώνευσης, μετονομάζουμε το πεδίο προσθέτοντας το "_Μετονομάστηκε» επίθημα.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Βήμα 4: Αποθήκευση του εγγράφου

 Τέλος, ονομάζουμε το`Save()` μέθοδος αποθήκευσης του τροποποιημένου εγγράφου.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Παράδειγμα πηγαίου κώδικα για μετονομασία πεδίων συγχώνευσης με το Aspose.Words για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργήστε το έγγραφο και εισαγάγετε τα πεδία συγχώνευσης.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Μετονομασία πεδίων συγχώνευσης.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Αποθηκεύστε το έγγραφο.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Ακολουθήστε αυτά τα βήματα για να μετονομάσετε τα πεδία συγχώνευσης στο έγγραφό σας χρησιμοποιώντας το Aspose.Words για .NET.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να μετονομάσω τα συγχωνευμένα πεδία σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να μετονομάσετε τα συγχωνευμένα πεδία σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να κάνετε κύκλο στα πεδία του εγγράφου χρησιμοποιώντας το`FieldMergingArgs` τάξη και χρησιμοποιήστε το`FieldMergingArgs.FieldName` μέθοδος μετονομασίας πεδίων.

#### Ε: Είναι δυνατόν να μετονομάσετε μόνο ορισμένα συγχωνευμένα πεδία σε ένα έγγραφο του Word με Aspose.Words για .NET;

Α: Ναι, είναι δυνατό να μετονομάσετε μόνο ορισμένα συγχωνευμένα πεδία σε ένα έγγραφο του Word με Aspose.Words για .NET. Μπορείτε να φιλτράρετε ποια πεδία θα μετονομάσετε χρησιμοποιώντας συγκεκριμένα κριτήρια, όπως το όνομα πεδίου ή άλλες σχετικές ιδιότητες. Στη συνέχεια, μπορείτε να μετονομάσετε τα αντίστοιχα πεδία χρησιμοποιώντας το`FieldMergingArgs.FieldName` μέθοδος.

#### Ε: Πώς μπορώ να ελέγξω εάν ένα συγχωνευμένο πεδίο μετονομάστηκε επιτυχώς σε ένα έγγραφο του Word με Aspose.Words για .NET;

 Α: Για να ελέγξετε εάν ένα συγχωνευμένο πεδίο μετονομάστηκε επιτυχώς σε ένα έγγραφο του Word με Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`FieldMergedArgs` τάξη και πρόσβαση στο`FieldMergedArgs.IsMerged` ιδιότητα για να προσδιορίσετε εάν το πεδίο μετονομάστηκε σε επίσκεψη.

#### Ε: Ποιες είναι οι συνέπειες της μετονομασίας ενός συγχωνευμένου πεδίου σε ένα έγγραφο του Word με Aspose.Words για .NET;

Α: Όταν μετονομάζετε ένα συγχωνευμένο πεδίο σε ένα έγγραφο του Word με Aspose.Words για .NET, αλλάζει το όνομα του πεδίου στο έγγραφο, γεγονός που μπορεί να επηρεάσει άλλες λειτουργίες ή διαδικασίες που εξαρτώνται από το όνομα του πεδίου. Φροντίστε να λάβετε υπόψη αυτές τις πιθανές συνέπειες πριν μετονομάσετε τα συγχωνευμένα πεδία.

#### Ε: Είναι δυνατή η επαναφορά του αρχικού ονόματος ενός συγχωνευμένου πεδίου μετά τη μετονομασία του σε Aspose.Words για .NET;

Α: Ναι, είναι δυνατό να επαναφέρετε το αρχικό όνομα ενός συγχωνευμένου πεδίου αφού το μετονομάσετε σε Aspose.Words για .NET. Μπορείτε να αποθηκεύσετε το αρχικό όνομα του πεδίου σε μια μεταβλητή ή λίστα και, στη συνέχεια, να χρησιμοποιήσετε αυτές τις πληροφορίες για να επαναφέρετε το αρχικό όνομα εάν χρειάζεται.