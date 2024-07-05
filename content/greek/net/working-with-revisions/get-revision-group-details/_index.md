---
title: Λάβετε λεπτομέρειες ομάδας αναθεώρησης
linktitle: Λάβετε λεπτομέρειες ομάδας αναθεώρησης
second_title: Aspose.Words Document Processing API
description: Λάβετε λεπτομέρειες ομάδας αναθεώρησης σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-revisions/get-revision-group-details/
---

Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας δείξουμε πώς μπορείτε να λάβετε τις λεπτομέρειες μιας ομάδας αναθεωρήσεων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας παρέχουμε τον πλήρη πηγαίο κώδικα και θα σας δείξουμε πώς να μορφοποιήσετε την έξοδο σήμανσης.

## Βήμα 1: Φόρτωση του εγγράφου

Το πρώτο βήμα είναι να ανεβάσετε το έγγραφο που περιέχει τις αναθεωρήσεις.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Βήμα 2: Περιήγηση σε αναθεωρήσεις

Στη συνέχεια, θα περιηγηθούμε στις αναθεωρήσεις που υπάρχουν στο έγγραφο και θα εμφανίσουμε τα στοιχεία τους, όπως τύπο, συγγραφέα, ημερομηνία και αναθεωρημένο κείμενο.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Παράδειγμα πηγαίου κώδικα για Λήψη λεπτομερειών ομάδας αναθεώρησης χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για να λάβετε τις λεπτομέρειες μιας ομάδας αναθεωρήσεων σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να λαμβάνουμε τις λεπτομέρειες μιας ομάδας αναθεωρήσεων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Χρησιμοποιώντας έναν βρόχο και τις κατάλληλες ιδιότητες, μπορέσαμε να εμφανίσουμε λεπτομέρειες όπως τον τύπο αναθεώρησης, τον συγγραφέα, την ημερομηνία και το αναθεωρημένο κείμενο. Το Aspose.Words για .NET προσφέρει πολλές ισχυρές δυνατότητες για τον χειρισμό εγγράφων του Word, συμπεριλαμβανομένης της διαχείρισης αναθεωρήσεων. Τώρα μπορείτε να χρησιμοποιήσετε αυτή τη γνώση για να λάβετε λεπτομέρειες ομάδας αναθεωρήσεων στα δικά σας έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να φορτώσω ένα έγγραφο με αναθεωρήσεις στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Document` κλάση Aspose.Words για .NET για τη φόρτωση ενός εγγράφου από ένα αρχείο που περιέχει αναθεωρήσεις. Μπορείτε να καθορίσετε την πλήρη διαδρομή του εγγράφου.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Ε: Πώς μπορώ να λάβω τις λεπτομέρειες μιας ομάδας αναθεωρήσεων στο Aspose.Words για .NET;

Α: Μεταβείτε στις αναθεωρήσεις του εγγράφου χρησιμοποιώντας έναν βρόχο και αποκτήστε πρόσβαση στις ιδιότητες κάθε αναθεώρησης για να λάβετε τις λεπτομέρειες που θέλετε. Μπορείτε να χρησιμοποιήσετε το`RevisionType`, `Author`, `DateTime` και`ParentNode` ιδιότητες για να λάβετε τον τύπο αναθεώρησης, τον συγγραφέα, την ημερομηνία και το αναθεωρημένο κείμενο αντίστοιχα.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Ε: Πώς να ελέγξετε εάν μια αναθεώρηση ανήκει σε μια ομάδα στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`Group` ιδιοκτησία του`Revision` αντικείμενο ελέγχου εάν μια αναθεώρηση ανήκει σε μια ομάδα. Αν το`Group` ιδιοκτησία είναι`null`, σημαίνει ότι η αναθεώρηση δεν ανήκει σε καμία ομάδα.

```csharp
if (revision.Group != null)
{
      // Η αναθεώρηση ανήκει σε μια ομάδα
}
else
{
      // Η αναθεώρηση δεν ανήκει σε καμία ομάδα
}
```