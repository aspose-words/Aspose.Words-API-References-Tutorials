---
title: Εισαγωγή πεδίου TOA χωρίς Εργαλείο δημιουργίας εγγράφων
linktitle: Εισαγωγή πεδίου TOA χωρίς Εργαλείο δημιουργίας εγγράφων
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την εισαγωγή πεδίου TOA χωρίς το Document Builder χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fields/insert-toafield-without-document-builder/
---

Ακολουθεί ένας βήμα προς βήμα οδηγός για να εξηγήσετε τον πηγαίο κώδικα C# παρακάτω, ο οποίος χρησιμοποιεί τη δυνατότητα "Εισαγωγή πεδίου TOA" του Aspose.Words για .NET. Ακολουθήστε κάθε βήμα προσεκτικά για να έχετε τα επιθυμητά αποτελέσματα.

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

## Βήμα 3: Εισαγωγή του πεδίου TA

Χρησιμοποιούμε την κλάση FieldTA για να εισαγάγουμε ένα πεδίο TA στην παράγραφο.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Βήμα 4: Προσθήκη της παραγράφου στο σώμα του εγγράφου

Προσθέτουμε την παράγραφο που περιέχει το πεδίο TA στο σώμα του εγγράφου.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Βήμα 5: Δημιουργία της παραγράφου για το πεδίο TOA

Δημιουργούμε μια νέα παράγραφο για το πεδίο TOA.

```csharp
para = new Paragraph(doc);
```

## Βήμα 6: Εισαγωγή του πεδίου TOA

Χρησιμοποιούμε την κλάση FieldToa για να εισαγάγουμε ένα πεδίο TOA στην παράγραφο.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Βήμα 7: Προσθήκη της παραγράφου στο σώμα του εγγράφου

Προσθέτουμε την παράγραφο που περιέχει το πεδίο TOA στο σώμα του εγγράφου.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Βήμα 8: Ενημερώστε το πεδίο TOA

 Τέλος, ονομάζουμε το`Update()` μέθοδο ενημέρωσης του πεδίου TOA.

```csharp
fieldToa.Update();
```

### Παράδειγμα πηγαίου κώδικα για εισαγωγή πεδίου TOA χωρίς Document Builder με Aspose.Words για .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Θέλουμε να εισαγάγουμε πεδία TA και TOA ως εξής:
// { TA \c 1 \l "Τιμή 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### Συχνές ερωτήσεις

#### Ε: Πώς να προσαρμόσετε την εμφάνιση του πεδίου TOA που έχει εισαχθεί στο έγγραφο του Word με το Aspose.Words για .NET;

Α: Μπορείτε να προσαρμόσετε την εμφάνιση του πεδίου TOA που έχει εισαχθεί χρησιμοποιώντας τις ιδιότητες του`FieldTOA` αντικείμενο για να καθορίσετε επιλογές μορφοποίησης.

#### Ε: Μπορώ να προσθέσω πολλά πεδία TOA σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

Α: Ναι, μπορείτε να προσθέσετε πολλά πεδία TOA σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Απλώς επαναλάβετε τα βήματα εισαγωγής για κάθε πεδίο.

#### Ε: Πώς μπορώ να ελέγξω εάν ένα πεδίο TOA εισήχθη με επιτυχία σε ένα έγγραφο του Word με Aspose.Words για .NET;

Α: Για να ελέγξετε εάν ένα πεδίο TOA εισήχθη με επιτυχία, μπορείτε να περιηγηθείτε στο περιεχόμενο του εγγράφου και να αναζητήσετε παρουσίες πεδίων TOA.

#### Ε: Η εισαγωγή ενός πεδίου TOA χωρίς τη χρήση του DocumentBuilder επηρεάζει τη μορφοποίηση εγγράφων του Word με το Aspose.Words για .NET;

Α: Η εισαγωγή ενός πεδίου TOA χωρίς τη χρήση του DocumentBuilder δεν επηρεάζει άμεσα τη μορφοποίηση του εγγράφου του Word. Ωστόσο, οι επιλογές μορφοποίησης πεδίου TOA μπορούν να επηρεάσουν τη συνολική μορφοποίηση του εγγράφου.