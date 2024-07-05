---
title: Μετακίνηση κόμβου σε έγγραφο παρακολούθησης
linktitle: Μετακίνηση κόμβου σε έγγραφο παρακολούθησης
second_title: Aspose.Words Document Processing API
description: Μετακινήστε τους κόμβους σε ένα έγγραφο παρακολούθησης με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-revisions/move-node-in-tracked-document/
---

Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας καθοδηγήσουμε πώς να μετακινήσετε έναν κόμβο σε ένα έγγραφο Word που παρακολουθείτε χρησιμοποιώντας το Aspose.Words για .NET. Θα σας παρέχουμε τον πλήρη πηγαίο κώδικα και θα σας δείξουμε πώς να μορφοποιήσετε την έξοδο σήμανσης.

## Βήμα 1: Δημιουργία του εγγράφου

Το πρώτο βήμα είναι να δημιουργήσετε ένα νέο έγγραφο και να προσθέσετε παραγράφους.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Βήμα 2: Παρακολούθηση αναθεωρήσεων

Θα ενεργοποιήσουμε την παρακολούθηση αναθεωρήσεων στο έγγραφο.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Βήμα 3: Μετακίνηση κόμβου

Θα μετακινήσουμε έναν κόμβο (παράγραφο) από τη μια θέση στην άλλη κατά τη δημιουργία αναθεωρήσεων.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Βήμα 4: Διακοπή παρακολούθησης κριτικών

Θα σταματήσουμε να παρακολουθούμε τις αναθεωρήσεις στο έγγραφο.

```csharp
doc.StopTrackRevisions();
```

## Βήμα 5: Αποθήκευση του εγγράφου

 Αφού εισαγάγετε το πεδίο φόρμας εισαγωγής κειμένου, αποθηκεύστε το έγγραφο στην επιθυμητή θέση χρησιμοποιώντας το`Save`μέθοδος. Φροντίστε να παρέχετε την κατάλληλη διαδρομή αρχείου:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Παράδειγμα πηγαίου κώδικα για Move Node In Tracked Document χρησιμοποιώντας Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη μετακίνηση ενός κόμβου σε ένα έγγραφο παρακολούθησης χρησιμοποιώντας το Aspose.Words για .NET:


```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Έναρξη παρακολούθησης αναθεωρήσεων.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Δημιουργήστε αναθεωρήσεις κατά τη μετακίνηση ενός κόμβου από μια τοποθεσία σε άλλη.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Διακοπή της διαδικασίας παρακολούθησης αναθεωρήσεων.
doc.StopTrackRevisions();

// Υπάρχουν 3 επιπλέον παράγραφοι στο εύρος μετακίνησης από.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να μετακινούμε έναν κόμβο σε ένα έγγραφο του Word που παρακολουθείται χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τα βήματα δημιουργίας του εγγράφου, ενεργοποιώντας την παρακολούθηση αναθεώρησης, μετακίνηση του κόμβου και διακοπή της παρακολούθησης αναθεώρησης, μπορέσαμε να εκτελέσουμε αυτόν τον χειρισμό με επιτυχία. Το Aspose.Words for .NET είναι ένα ισχυρό εργαλείο για την επεξεργασία λέξεων με έγγραφα του Word και προσφέρει προηγμένες δυνατότητες για τη διαχείριση αναθεωρήσεων. Τώρα μπορείτε να χρησιμοποιήσετε αυτή τη γνώση για να μετακινήσετε κόμβους στα δικά σας έγγραφα του Word ενώ παρακολουθείτε τις αναθεωρήσεις χρησιμοποιώντας το Aspose.Words για .NET.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να ενεργοποιήσω την παρακολούθηση αναθεωρήσεων σε ένα έγγραφο Aspose.Words για .NET;

 Α: Για να ενεργοποιήσετε την παρακολούθηση αναθεωρήσεων σε ένα έγγραφο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`StartTrackRevisions` μέθοδος του`Document` αντικείμενο. Αυτή η μέθοδος λαμβάνει ως παραμέτρους το όνομα του συντάκτη των αναθεωρήσεων και την ημερομηνία έναρξης της παρακολούθησης των αναθεωρήσεων.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### Ε: Πώς μπορώ να μετακινήσω έναν κόμβο σε ένα έγγραφο που παρακολουθείται χωρίς να δημιουργήσω αναθεωρήσεις;

 Α: Εάν θέλετε να μετακινήσετε έναν κόμβο σε ένα έγγραφο παρακολούθησης χωρίς να δημιουργήσετε αναθεωρήσεις, μπορείτε να χρησιμοποιήσετε το`Remove` και`InsertAfter` ή`InsertBefore` μεθόδους του`Node` αντικείμενο. Για παράδειγμα, για να μετακινήσετε μια παράγραφο μετά από μια άλλη παράγραφο, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### Ε: Πώς μπορώ να σταματήσω την παρακολούθηση αναθεωρήσεων σε ένα έγγραφο Aspose.Words για .NET;

 Α: Για να σταματήσετε την παρακολούθηση αναθεωρήσεων σε ένα έγγραφο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`StopTrackRevisions` μέθοδος του`Document` αντικείμενο.

```csharp
doc.StopTrackRevisions();
```