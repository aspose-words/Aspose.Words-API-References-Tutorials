---
title: Πρόσβαση στην αναθεωρημένη έκδοση
linktitle: Πρόσβαση στην αναθεωρημένη έκδοση
second_title: Aspose.Words Document Processing API
description: Αποκτήστε πρόσβαση σε μια αναθεωρημένη έκδοση ενός εγγράφου του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-revisions/access-revised-version/
---

Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας δείξουμε πώς να αποκτήσετε πρόσβαση στην αναθεωρημένη έκδοση ενός εγγράφου του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας παρέχουμε τον πλήρη πηγαίο κώδικα και θα σας δείξουμε πώς να μορφοποιήσετε την έξοδο σήμανσης.

## Βήμα 1: Φόρτωση του εγγράφου

Το πρώτο βήμα είναι να ανεβάσετε το έγγραφο που περιέχει τις αναθεωρήσεις.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Βήμα 2: Πρόσβαση στην αναθεωρημένη έκδοση

Θα προχωρήσουμε τώρα στην αναθεωρημένη έκδοση του εγγράφου.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Βήμα 3: Περιήγηση σε αναθεωρήσεις

Στη συνέχεια, θα διερευνήσουμε τις αναθεωρήσεις που υπάρχουν στο έγγραφο και θα εμφανίσουμε συγκεκριμένες πληροφορίες για παραγράφους που είναι στοιχεία λίστας.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Παράδειγμα πηγαίου κώδικα για την αναθεωρημένη έκδοση της Access χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για πρόσβαση στην αναθεωρημένη έκδοση ενός εγγράφου χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Μεταβείτε στην αναθεωρημένη έκδοση του εγγράφου.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να έχουμε πρόσβαση στην αναθεωρημένη έκδοση ενός εγγράφου του Word χρησιμοποιώντας το Aspose.Words για .NET. Με τη φόρτωση του εγγράφου, την πλοήγηση στην αναθεωρημένη έκδοση και την περιήγηση στις αναθεωρήσεις, μπορέσαμε να λάβουμε συγκεκριμένες πληροφορίες για παραγράφους που αποτελούν στοιχεία λίστας. Το Aspose.Words για .NET προσφέρει ισχυρές δυνατότητες για χειρισμό εγγράφων του Word, συμπεριλαμβανομένης της πρόσβασης σε κριτικές. Τώρα μπορείτε να χρησιμοποιήσετε αυτήν τη γνώση για να αποκτήσετε πρόσβαση στην αναθεωρημένη έκδοση των δικών σας εγγράφων Word χρησιμοποιώντας το Aspose.Words για .NET.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να φορτώσω ένα έγγραφο με αναθεωρήσεις στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Document` κλάση Aspose.Words για .NET για τη φόρτωση ενός εγγράφου από ένα αρχείο που περιέχει αναθεωρήσεις. Μπορείτε να καθορίσετε την πλήρη διαδρομή του εγγράφου.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Ε: Πώς μπορώ να αποκτήσω πρόσβαση στην αναθεωρημένη έκδοση ενός εγγράφου στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`RevisionsView` ιδιοκτησία του`Document` αντίρρηση πρόσβασης στην αναθεωρημένη έκδοση του εγγράφου. Μπορείτε να ορίσετε την τιμή του`RevisionsView`ιδιοκτησία σε`RevisionsView.Final` για να εμφανιστεί η τελική έκδοση χωρίς τις αναθεωρήσεις.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Ε: Πώς μπορώ να περιηγηθώ σε αναθεωρήσεις εγγράφων στο Aspose.Words για .NET;

Α: Χρησιμοποιήστε α`foreach` βρόχο για επανάληψη μέσω των αναθεωρήσεων που υπάρχουν στο έγγραφο. Μπορείτε να χρησιμοποιήσετε το`Revisions` ιδιοκτησία του`Document` αντικείμενο να λάβετε μια συλλογή από όλες τις αναθεωρήσεις του εγγράφου.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Επεξεργαστείτε κάθε αναθεώρηση εδώ
}
```

#### Ε: Πώς να ελέγξετε εάν μια παράγραφος είναι ένα στοιχείο λίστας στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`IsListItem` ιδιοκτησία του`Paragraph` αντικείμενο για να ελέγξετε εάν μια παράγραφος είναι ένα στοιχείο λίστας. ο`IsListItem` επιστροφές ακινήτων`true` εάν η παράγραφος είναι στοιχείο λίστας, διαφορετικά επιστρέφει`false`.

```csharp
if (paragraph.IsListItem)
{
     // Η παράγραφος είναι ένα στοιχείο λίστας
}
else
{
     // Η παράγραφος δεν είναι στοιχείο λίστας
}
```