---
title: Φόρτωση εύρους σελίδων σε μορφή Pdf
linktitle: Φόρτωση εύρους σελίδων σε μορφή Pdf
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη φόρτωση μιας συγκεκριμένης περιοχής σελίδων PDF με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον τρόπο φόρτωσης μιας συγκεκριμένης περιοχής σελίδων από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθήστε τα παρακάτω βήματα:

## Βήμα 1: Φόρτωση μιας σειράς σελίδων PDF

Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε μια συγκεκριμένη περιοχή σελίδων από ένα έγγραφο PDF:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Σε αυτό το παράδειγμα, φορτώνουμε την πρώτη σελίδα του εγγράφου PDF. Μπορείτε να αλλάξετε τις τιμές του`PageIndex` και`PageCount` στο επιθυμητό εύρος σελίδων.

## Βήμα 2: Αποθήκευση του εγγράφου

 Τέλος, μπορείτε να αποθηκεύσετε το έγγραφο που περιέχει τη συγκεκριμένη περιοχή σελίδων χρησιμοποιώντας το`Save` μέθοδος:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή για την αποθήκευση του επεξεργασμένου εγγράφου.

Αυτό είναι όλο ! Τώρα έχετε φορτώσει μια συγκεκριμένη περιοχή σελίδων από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για Load Page Range Of Pdf χρησιμοποιώντας Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Θυμηθείτε να καθορίσετε τη σωστή διαδρομή προς τον κατάλογο των εγγράφων PDF σας.



