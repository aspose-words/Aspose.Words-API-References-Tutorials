---
title: Εισαγάγετε το αντικείμενο Ole στο έγγραφο του Word ως εικονίδιο
linktitle: Εισαγάγετε το αντικείμενο Ole στο έγγραφο του Word ως εικονίδιο
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισάγετε ένα αντικείμενο OLE στο έγγραφο του Word ως εικονίδιο με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Ακολουθεί ένας οδηγός βήμα προς βήμα για να εξηγήσετε τον πηγαίο κώδικα C# παρακάτω, ο οποίος δείχνει πώς να εισαγάγετε ένα αντικείμενο OLE στο έγγραφο του Word ως εικονίδιο χρησιμοποιώντας το Aspose.Words για .NET.

## Βήμα 1: Εισαγάγετε τις απαραίτητες αναφορές
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες αναφορές για να χρησιμοποιήσετε το Aspose.Words για .NET στο έργο σας. Αυτό περιλαμβάνει την εισαγωγή της βιβλιοθήκης Aspose.Words και την προσθήκη των απαιτούμενων χώρων ονομάτων στο αρχείο προέλευσης.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Βήμα 2: Δημιουργήστε ένα νέο πρόγραμμα δημιουργίας εγγράφων και εγγράφων
 Σε αυτό το βήμα, θα δημιουργήσουμε ένα νέο έγγραφο χρησιμοποιώντας το`Document` κλάση και ένα πρόγραμμα δημιουργίας εγγράφων χρησιμοποιώντας το`DocumentBuilder` τάξη.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Εισαγάγετε ένα αντικείμενο OLE ως εικονίδιο
 Χρησιμοποιήστε το Document Builder's`InsertOleObjectAsIcon` μέθοδος για την εισαγωγή ενός αντικειμένου OLE ως εικονίδιο στο έγγραφο. Καθορίστε τη διαδρομή αρχείου OLE, τη σημαία εμφάνισης, τη διαδρομή εικονιδίου και το όνομα του ενσωματωμένου αντικειμένου.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
 Χρησιμοποιήστε το έγγραφο`Save` μέθοδο αποθήκευσης του εγγράφου σε αρχείο.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Παράδειγμα πηγαίου κώδικα για την εισαγωγή ενός αντικειμένου OLE ως εικονίδιο με το Aspose.Words για .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Αυτό είναι ένα πλήρες δείγμα κώδικα για την εισαγωγή ενός αντικειμένου OLE ως εικονίδιο με το Aspose.Words για .NET. Φροντίστε να εισαγάγετε τις απαραίτητες αναφορές και ακολουθήστε τα βήματα που περιγράφηκαν προηγουμένως για να ενσωματώσετε αυτόν τον κώδικα στο έργο σας.

## συμπέρασμα

Εν κατακλείδι, εξερευνήσαμε έναν οδηγό βήμα προς βήμα για την εισαγωγή ενός αντικειμένου OLE ως εικονίδιο σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.

Ακολουθώντας αυτά τα βήματα, θα είστε σε θέση να εισαγάγετε με επιτυχία ένα αντικείμενο OLE ως εικονίδιο στα έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET. Φροντίστε να εισαγάγετε τις απαραίτητες αναφορές και ακολουθήστε προσεκτικά τις οδηγίες για να έχετε τα επιθυμητά αποτελέσματα.

### Συχνές ερωτήσεις για την εισαγωγή αντικειμένου ole στο έγγραφο του Word ως εικονίδιο

#### Ε. Ποιες αναφορές χρειάζονται για να εισαγάγετε ένα αντικείμενο OLE ως εικονίδιο σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

Α: Πρέπει να εισαγάγετε τις ακόλουθες αναφορές στο έργο σας για να χρησιμοποιήσετε το Aspose.Words για .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Ε. Πώς να δημιουργήσετε ένα νέο πρόγραμμα δημιουργίας εγγράφων και εγγράφων στο Aspose.Words για .NET;

 Α: Μπορείτε να δημιουργήσετε ένα νέο έγγραφο χρησιμοποιώντας το`Document` κλάση και ένα πρόγραμμα δημιουργίας εγγράφων χρησιμοποιώντας το`DocumentBuilder`τάξη. Εδώ είναι ένα παράδειγμα:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Ε. Πώς να εισαγάγετε ένα αντικείμενο OLE ως εικονίδιο στο έγγραφο;

 A: Χρησιμοποιήστε το Document Builder's`InsertOleObjectAsIcon` μέθοδο εισαγωγής ενός αντικειμένου OLE ως εικονίδιο. Καθορίστε τη διαδρομή αρχείου OLE, τη σημαία εμφάνισης, τη διαδρομή εικονιδίου και το όνομα του ενσωματωμένου αντικειμένου. Εδώ είναι ένα παράδειγμα:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Ε. Πώς να αποθηκεύσετε το έγγραφο με το αντικείμενο OLE να έχει εισαχθεί ως εικονίδιο;

 Α: Χρησιμοποιήστε το έγγραφο`Save`μέθοδο αποθήκευσης του εγγράφου σε αρχείο. Εδώ είναι ένα παράδειγμα:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```