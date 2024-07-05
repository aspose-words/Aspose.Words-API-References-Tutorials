---
title: Αναθεώρηση σχήματος
linktitle: Αναθεώρηση σχήματος
second_title: Aspose.Words Document Processing API
description: Αναθεωρήστε τα σχήματα σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-revisions/shape-revision/
---

Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας καθοδηγήσουμε πώς να κάνετε αναθεωρήσεις σε σχήματα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας παρέχουμε τον πλήρη πηγαίο κώδικα και θα σας δείξουμε πώς να μορφοποιήσετε την έξοδο σήμανσης.

## Βήμα 1: Δημιουργία του εγγράφου και προσθήκη σχημάτων

Το πρώτο βήμα είναι να δημιουργήσετε ένα νέο έγγραφο και να προσθέσετε σχήματα.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Βήμα 2: Παρακολουθήστε τις αναθεωρήσεις και προσθέστε ένα άλλο σχήμα

Θα ενεργοποιήσουμε την παρακολούθηση αναθεωρήσεων και θα προσθέσουμε ένα άλλο σχήμα.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Βήμα 3: Αποκτήστε τη συλλογή σχημάτων και ελέγξτε για αναθεωρήσεις

Θα λάβουμε τη συλλογή σχημάτων από το έγγραφο και θα ελέγξουμε τις αναθεωρήσεις που σχετίζονται με κάθε σχήμα.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Βήμα 4: Έλεγχος των αναθεωρήσεων μετακίνησης σχήματος

Θα φορτώσουμε ένα υπάρχον έγγραφο που περιέχει αναθεωρήσεις μετατόπισης σχήματος και θα ελέγξουμε τις σχετικές αναθεωρήσεις.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Παράδειγμα πηγαίου κώδικα για το Shape Revision χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για την πραγματοποίηση αναθεωρήσεων σε σχήματα σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
Document doc = new Document();

//Εισαγάγετε ένα ενσωματωμένο σχήμα χωρίς παρακολούθηση αναθεωρήσεων.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Ξεκινήστε την παρακολούθηση αναθεωρήσεων και, στη συνέχεια, εισαγάγετε ένα άλλο σχήμα.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Αποκτήστε τη συλλογή σχημάτων του εγγράφου που περιλαμβάνει μόνο τα δύο σχήματα που προσθέσαμε.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Αφαιρέστε το πρώτο σχήμα.
shapes[0].Remove();

// Επειδή καταργήσαμε αυτό το σχήμα ενώ παρακολουθούνταν οι αλλαγές, το σχήμα υπολογίζεται ως αναθεώρηση διαγραφής.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Και εισαγάγαμε ένα άλλο σχήμα κατά την παρακολούθηση αλλαγών, έτσι ώστε αυτό το σχήμα να υπολογίζεται ως αναθεώρηση ένθετου.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Το έγγραφο έχει ένα σχήμα που μετακινήθηκε, αλλά οι αναθεωρήσεις μετακίνησης σχήματος θα έχουν δύο περιπτώσεις αυτού του σχήματος.
// Το ένα θα είναι το σχήμα στον προορισμό άφιξης του και το άλλο θα είναι το σχήμα στην αρχική του θέση.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Αυτή είναι η κίνηση προς την αναθεώρηση, αλλά και το σχήμα στον προορισμό άφιξης.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Αυτή είναι η κίνηση από την αναθεώρηση, που είναι το σχήμα στην αρχική του θέση.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να κάνουμε αναθεωρήσεις σχημάτων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τα βήματα δημιουργίας του εγγράφου, ενεργοποιώντας την παρακολούθηση αναθεωρήσεων, ελέγχοντας τις αναθεωρήσεις που σχετίζονται με κάθε σχήμα και ελέγχοντας τις αναθεωρήσεις για τη μετακίνηση των σχημάτων, μπορέσαμε να διαχειριστούμε τις αναθεωρήσεις με επιτυχία. Το Aspose.Words για .NET προσφέρει ένα ισχυρό API για επεξεργασία λέξεων με κριτικές και φόρμες σε έγγραφα του Word.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να δημιουργήσω ένα νέο έγγραφο και να προσθέσω σχήματα στο Aspose.Words για .NET;

Α: Για να δημιουργήσετε ένα νέο έγγραφο και να προσθέσετε σχήματα στο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα. Εδώ προσθέτουμε δύο σχήματα, έναν κύβο και έναν ήλιο, στην πρώτη ενότητα του εγγράφου:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Ε: Πώς μπορώ να ενεργοποιήσω την παρακολούθηση αναθεωρήσεων στο Aspose.Words για .NET;

 Α: Για να ενεργοποιήσετε την παρακολούθηση αναθεωρήσεων στο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`StartTrackRevisions` μέθοδος του`Document` αντικείμενο. Αυτή η μέθοδος λαμβάνει ως παράμετρο το όνομα του συγγραφέα των αναθεωρήσεων:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Ε: Πώς μπορώ να ελέγξω τις αναθεωρήσεις που σχετίζονται με κάθε σχήμα σε ένα έγγραφο Aspose.Words για .NET;

Α: Για να ελέγξετε τις αναθεωρήσεις που σχετίζονται με κάθε σχήμα σε ένα έγγραφο Aspose.Words για .NET, μπορείτε να λάβετε τη συλλογή σχημάτων του εγγράφου χρησιμοποιώντας το`GetChildNodes` μέθοδος με το`NodeType.Shape` τύπος κόμβου. Στη συνέχεια, μπορείτε να αποκτήσετε πρόσβαση σε κάθε σχήμα`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , και`IsMoveToRevision` ιδιότητες για τον προσδιορισμό του τύπου αναθεώρησης που σχετίζεται με το σχήμα:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Ε: Πώς μπορώ να ελέγξω για αναθεωρήσεις μετατόπισης σχημάτων σε ένα έγγραφο Aspose.Words για .NET;

 Α: Για να ελέγξετε για αναθεωρήσεις μετατόπισης σχήματος σε ένα έγγραφο Aspose.Words για .NET, μπορείτε να φορτώσετε ένα υπάρχον έγγραφο που περιέχει αναθεωρήσεις μετατόπισης σχήματος. Στη συνέχεια, μπορείτε να αποκτήσετε πρόσβαση σε κάθε σχήμα`IsMoveFromRevision` και`IsMoveToRevision` ιδιότητες για να προσδιορίσετε εάν μετακινείται και εάν ναι, από πού και πού:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```