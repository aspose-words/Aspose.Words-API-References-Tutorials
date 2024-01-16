---
title: Εικόνα
linktitle: Εικόνα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισάγετε και να προσαρμόζετε εικόνα με το Aspose.Words for .NET Βήμα προς βήμα οδηγό.
type: docs
weight: 10
url: /el/net/working-with-markdown/image/
---

Σε αυτό το παράδειγμα, θα εξηγήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα εικόνας με το Aspose.Words για .NET. Οι εικόνες σάς επιτρέπουν να εισάγετε εικόνες και γραφικά σε ένα έγγραφο.

## Βήμα 1: Χρήση ενός προγράμματος δημιουργίας εγγράφων

Αρχικά, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Βήμα 2: Εισαγωγή εικόνας

 Μπορούμε να εισάγουμε μια εικόνα χρησιμοποιώντας το`Shape` τάξη και προσδιορίζοντας τον τύπο της εικόνας, εδώ`ShapeType.Image` Ορίζουμε επίσης τον τύπο αναδίπλωσης της εικόνας σε`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Βήμα 3: Προσαρμογή εικόνας

 Προσαρμόζουμε την εικόνα, για παράδειγμα, προσδιορίζοντας την πλήρη διαδρομή της`"/attachment/1456/pic001.png"`και προσθέτοντας έναν τίτλο στην εικόνα.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Παράδειγμα πηγαίου κώδικα για εικόνες με Aspose.Words για .NET

```csharp
// Χρησιμοποιήστε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσετε περιεχόμενο στο έγγραφο.
DocumentBuilder builder = new DocumentBuilder();

// Εισαγωγή εικόνας.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Συγχαρητήρια ! Τώρα έχετε μάθει πώς να χρησιμοποιείτε τη δυνατότητα εικόνων με το Aspose.Words για .NET.


### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να εισαγάγω μια εικόνα από ένα τοπικό αρχείο στο Aspose.Words;

 Α: Για να εισαγάγετε μια εικόνα από ένα τοπικό αρχείο στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`Shape` τάξη και το`InsertImage` μέθοδος.

#### Ε: Μπορώ να εισαγάγω μια εικόνα από μια διεύθυνση URL στο Aspose.Words;

 Α: Ναι, μπορείτε να εισαγάγετε μια εικόνα από μια διεύθυνση URL στο Aspose.Words. Μπορείτε να χρησιμοποιήσετε το ίδιο`InsertImage` μέθοδο και καθορίστε τη διεύθυνση URL της εικόνας αντί για την τοπική διαδρομή αρχείου.

#### Ε: Πώς μπορώ να αλλάξω το μέγεθος μιας εικόνας στο Aspose.Words;

 Α: Για να αλλάξετε το μέγεθος μιας εικόνας στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`Width` και`Height` ιδιότητες του`Shape` αντικείμενο.

#### Ε: Μπορώ να εφαρμόσω φίλτρα σε εικόνες στο Aspose.Words;

Α: Ναι, μπορείτε να εφαρμόσετε φίλτρα σε εικόνες στο Aspose.Words. Για παράδειγμα, μπορείτε να εφαρμόσετε ένα φίλτρο θαμπώματος σε μια εικόνα χρησιμοποιώντας το`ApplyGaussianBlur` μέθοδος του`Shape` αντικείμενο.

#### Ε: Πώς μπορώ να αντικαταστήσω μια εικόνα με μια άλλη στο Aspose.Words;

 Α: Για να αντικαταστήσετε μια εικόνα με μια άλλη στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`Replace` μέθοδος του`Shape` τάξη. Αυτή η μέθοδος λαμβάνει ως παράμετρο το`Shape` αντικείμενο της εικόνας που θα αντικατασταθεί και το`Shape` αντικείμενο της νέας εικόνας.