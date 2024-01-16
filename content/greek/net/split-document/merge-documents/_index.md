---
title: Συγχώνευση εγγράφων του Word
linktitle: Συγχώνευση εγγράφων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να συγχωνεύετε πολλά έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET. Αυτό το ισχυρό API απλοποιεί τη διαδικασία συγχώνευσης εγγράφων, καθιστώντας το αποτελεσματικό και απλό.
type: docs
weight: 10
url: /el/net/split-document/merge-documents/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον τρόπο συγχώνευσης πολλών εγγράφων του Word χρησιμοποιώντας τη δυνατότητα Συγχώνευσης εγγράφων του Aspose.Words για .NET. Ακολουθήστε τα παρακάτω βήματα για να κατανοήσετε τον πηγαίο κώδικα και να λάβετε ένα συγχωνευμένο έγγραφο που περιέχει όλα τα έγγραφα προέλευσης.

## Βήμα 1: Αναζήτηση εγγράφων για συγχώνευση

Πριν από τη συγχώνευση των εγγράφων, πρέπει να εντοπίσουμε τα έγγραφα προέλευσης που πρόκειται να συγχωνευθούν. Δείτε πώς:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Αναζήτηση εγγράφων για συγχώνευση.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Βήμα 2: Συγχώνευση εγγράφων

Τώρα θα συγχωνεύσουμε τα έγγραφα ένα προς ένα για να δημιουργήσουμε ένα τελικό συγχωνευμένο έγγραφο. Δείτε πώς:

```csharp
// Ανοίξτε το πρώτο μέρος του εγγράφου που προκύπτει.
Document sourceDoc = new Document(sourceDocumentPath);

// Δημιουργήστε ένα νέο έγγραφο που προκύπτει.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Συγχωνεύστε τα έγγραφα ένα προς ένα.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Παράδειγμα πηγαίου κώδικα για συγχώνευση εγγράφων με χρήση του Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δυνατότητα Συγχώνευσης Εγγράφων του Aspose.Words για .NET:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Βρείτε έγγραφα χρησιμοποιώντας για συγχώνευση.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Ανοίξτε το πρώτο μέρος του εγγράφου που προκύπτει.
Document sourceDoc = new Document(sourceDocumentPath);

// Δημιουργήστε ένα νέο έγγραφο που προκύπτει.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Συγχώνευση τμημάτων εγγράφου ένα προς ένα.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## συμπέρασμα

Συγχαρητήρια! Έχετε μάθει πώς να συγχωνεύετε πολλά έγγραφα του Word χρησιμοποιώντας τη δυνατότητα Συγχώνευσης εγγράφων του Aspose.Words για .NET. Ακολουθώντας τον παρεχόμενο πηγαίο κώδικα, μπορείτε να συνδυάσετε ξεχωριστά έγγραφα σε ένα ενιαίο συγχωνευμένο έγγραφο, διατηρώντας παράλληλα τη μορφοποίηση κάθε εγγράφου προέλευσης.

Η συγχώνευση εγγράφων μπορεί να είναι χρήσιμη όταν θέλετε να ενοποιήσετε πληροφορίες από πολλές πηγές ή να δημιουργήσετε ένα ενοποιημένο έγγραφο από μεμονωμένα μέρη. Το Aspose.Words για .NET παρέχει ένα ισχυρό API που απλοποιεί τη διαδικασία συγχώνευσης εγγράφων, καθιστώντας το αποτελεσματικό και απλό.

Μη διστάσετε να εξερευνήσετε άλλες δυνατότητες που προσφέρει το Aspose.Words για .NET για να βελτιώσετε τις δυνατότητες επεξεργασίας εγγράφων σας και να βελτιώσετε τη ροή εργασίας σας.

### Συχνές ερωτήσεις

#### Πώς μπορώ να συγχωνεύσω έγγραφα με διαφορετική μορφοποίηση;

 Κατά τη συγχώνευση εγγράφων, το Aspose.Words για .NET παρέχει την επιλογή διατήρησης της μορφοποίησης κάθε εγγράφου προέλευσης. Με τη χρήση του`ImportFormatMode.KeepSourceFormatting` επιλογή, το συγχωνευμένο έγγραφο θα διατηρήσει τη μορφοποίηση των αρχικών εγγράφων. Εάν θέλετε να εφαρμόσετε συνεπή μορφοποίηση σε όλο το συγχωνευμένο έγγραφο, μπορείτε να τροποποιήσετε τη μορφοποίηση χρησιμοποιώντας το Aspose.Words API μετά τη συγχώνευση των εγγράφων.

#### Μπορώ να συγχωνεύσω έγγραφα σε διαφορετικές μορφές;

Ναι, το Aspose.Words για .NET υποστηρίζει τη συγχώνευση εγγράφων σε διάφορες μορφές, συμπεριλαμβανομένων των DOCX, DOC, RTF και άλλων. Μπορείτε να φορτώσετε έγγραφα διαφορετικών μορφών στο Aspose.Words API και να τα συγχωνεύσετε σε ένα μόνο έγγραφο ανεξάρτητα από την αρχική τους μορφή.

#### Μπορώ να συγχωνεύσω έγγραφα με πολύπλοκες δομές, όπως πίνακες και εικόνες;

Απολύτως! Το Aspose.Words για .NET έχει τη δυνατότητα να συγχωνεύει έγγραφα με πολύπλοκες δομές, όπως πίνακες, εικόνες, κεφαλίδες, υποσέλιδα και άλλα. Το API χειρίζεται τη διαδικασία συγχώνευσης, διατηρώντας παράλληλα την ακεραιότητα και τη διάταξη του περιεχομένου σε κάθε έγγραφο.

#### Είναι δυνατή η συγχώνευση εγγράφων με διαφορετικούς προσανατολισμούς ή μεγέθη σελίδας;

Ναι, το Aspose.Words για .NET χειρίζεται έγγραφα με διαφορετικούς προσανατολισμούς ή μεγέθη σελίδας κατά τη διαδικασία συγχώνευσης. Το προκύπτον συγχωνευμένο έγγραφο θα φιλοξενήσει τους ποικίλους προσανατολισμούς και μεγέθη σελίδας των εγγράφων προέλευσης.