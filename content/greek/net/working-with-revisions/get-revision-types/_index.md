---
title: Λάβετε τύπους λέξεων αναθεώρησης
linktitle: Λάβετε τύπους λέξεων αναθεώρησης
second_title: Aspose.Words Document Processing API
description: Λάβετε τύπους αναθεώρησης λέξεων σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-revisions/get-revision-types/
---

Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας πούμε πώς να λαμβάνετε τους τύπους αναθεωρήσεων λέξεων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας παρέχουμε τον πλήρη πηγαίο κώδικα και θα σας δείξουμε πώς να μορφοποιήσετε την έξοδο σήμανσης.

## Βήμα 1: Φόρτωση του εγγράφου

Το πρώτο βήμα είναι να ανεβάσετε το έγγραφο που περιέχει τις αναθεωρήσεις.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Βήμα 2: Βήμα μέσα από τις παραγράφους

Στη συνέχεια, θα εξετάσουμε τις παραγράφους του εγγράφου και θα ελέγξουμε τους τύπους των αναθεωρήσεων λέξεων που σχετίζονται με κάθε παράγραφο.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Παράδειγμα πηγαίου κώδικα για Λήψη τύπων αναθεώρησης χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη λήψη τύπων αναθεώρησης σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να λαμβάνουμε τους τύπους αναθεωρήσεων λέξεων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθήσαμε τα βήματα για να φορτώσουμε το έγγραφο, να διαβάσουμε τις παραγράφους και να ελέγξουμε τους τύπους κριτικών λέξεων που σχετίζονται με κάθε παράγραφο. Τώρα μπορείτε να εφαρμόσετε αυτή τη γνώση για να αναλύσετε κριτικές λέξεων στα δικά σας έγγραφα Word χρησιμοποιώντας το Aspose.Words για .NET.

### Συχνές ερωτήσεις για τη λήψη τύπων αναθεώρησης λέξεων

#### Ε: Πώς να ανεβάσετε ένα έγγραφο στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Document` κλάση Aspose.Words για .NET για τη φόρτωση ενός εγγράφου από ένα αρχείο. Μπορείτε να καθορίσετε την πλήρη διαδρομή του εγγράφου.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Ε: Πώς μπορώ να πραγματοποιήσω επαναφορά παραγράφων σε ένα έγγραφο στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Paragraphs` ιδιοκτησία της ενότητας εγγράφου για να λάβετε τη συλλογή των παραγράφων. Στη συνέχεια, μπορείτε να χρησιμοποιήσετε έναν βρόχο για να κάνετε βρόχο σε κάθε παράγραφο.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Επεξεργαστείτε κάθε παράγραφο εδώ
}
```

#### Ε: Πώς μπορώ να ελέγξω εάν μια παράγραφος έχει μετακινηθεί (διαγραφεί) στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε μια παράγραφο`IsMoveFromRevision` ιδιοκτησία για να ελέγξετε εάν έχει μετακινηθεί (διαγραφεί).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Η παράγραφος έχει μετακινηθεί (διαγράφηκε)
}
```

#### Ε: Πώς να ελέγξετε εάν μια παράγραφος έχει μετακινηθεί (εισαχθεί) στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε μια παράγραφο`IsMoveToRevision`ιδιοκτησία για να ελέγξετε αν έχει μετακινηθεί (εισαχθεί).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Η παράγραφος έχει μετακινηθεί (εισαχθεί)
}
```