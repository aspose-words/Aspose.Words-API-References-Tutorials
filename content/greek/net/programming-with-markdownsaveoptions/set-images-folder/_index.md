---
title: Ορισμός φακέλου εικόνων
linktitle: Ορισμός φακέλου εικόνων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ορίζετε το φάκελο εικόνων κατά την εξαγωγή στο Markdown με το Aspose.Words για .NET. Προσαρμόστε την τοποθέτηση των εικόνων για καλύτερη οργάνωση και ενσωμάτωση.
type: docs
weight: 10
url: /el/net/programming-with-markdownsaveoptions/set-images-folder/
---

Ακολουθεί ένας οδηγός βήμα προς βήμα για να εξηγήσετε τον ακόλουθο πηγαίο κώδικα C# που βοηθά στον ορισμό του φακέλου εικόνων για επιλογές εξαγωγής Markdown χρησιμοποιώντας τη βιβλιοθήκη Aspose.Words για .NET. Βεβαιωθείτε ότι έχετε συμπεριλάβει τη βιβλιοθήκη Aspose.Words στο έργο σας πριν χρησιμοποιήσετε αυτόν τον κώδικα.

## Βήμα 1: Ορισμός διαδρομής καταλόγου εγγράφων

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο των εγγράφων σας όπου βρίσκεται το έγγραφο που περιέχει τις εικόνες.

## Βήμα 2: Φορτώστε το έγγραφο που περιέχει τις εικόνες

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Φορτώνουμε το καθορισμένο έγγραφο που περιέχει τις εικόνες που θέλουμε να εξαγάγουμε με τις επιλογές Markdown.

## Βήμα 3: Ορίστε το φάκελο εικόνων για επιλογές εξαγωγής Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Δημιουργούμε ένα παράδειγμα του`MarkdownSaveOptions` και ορίστε τη διαδρομή προς το φάκελο εικόνων χρησιμοποιώντας το`ImagesFolder` ιδιοκτησία. Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς το φάκελο όπου θέλετε να αποθηκεύσετε τις εξαγόμενες εικόνες.

## Βήμα 4: Αποθηκεύστε το έγγραφο με τις επιλογές εξαγωγής Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Αποθηκεύουμε το έγγραφο σε μια ροή μνήμης χρησιμοποιώντας τις καθορισμένες επιλογές εξαγωγής Markdown. Στη συνέχεια, μπορείτε να χρησιμοποιήσετε τη ροή για να εκτελέσετε άλλες λειτουργίες, όπως την αποθήκευση περιεχομένου Markdown σε ένα αρχείο.

### Παράδειγμα πηγαίου κώδικα για να ορίσετε το φάκελο εικόνων για MarkdownSaveOptions με Aspose.Words για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Αυτός ο πηγαίος κώδικας δείχνει πώς να φορτώσετε ένα έγγραφο που περιέχει εικόνες και στη συνέχεια να ορίσετε τον φάκελο εικόνων για επιλογές εξαγωγής Markdown. Χρησιμοποιώντας τις καθορισμένες επιλογές, το έγγραφο αποθηκεύεται στη συνέχεια σε μια ροή μνήμης. Αυτό σας επιτρέπει να προσαρμόσετε τη θέση του φακέλου εικόνων κατά την εξαγωγή περιεχομένου Markdown.