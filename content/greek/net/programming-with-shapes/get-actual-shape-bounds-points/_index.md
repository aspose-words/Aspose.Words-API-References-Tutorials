---
title: Λάβετε πόντους πραγματικών ορίων σχήματος
linktitle: Λάβετε πόντους πραγματικών ορίων σχήματος
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ανακτάτε τα πραγματικά όρια ενός σχήματος σε σημεία (μονάδα μέτρησης) σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Αυτό το σεμινάριο εξηγεί πώς να ανακτήσετε τα πραγματικά όρια ενός σχήματος σε σημεία (μονάδα μέτρησης) σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Τα όρια αντιπροσωπεύουν το μέγεθος και τη θέση του σχήματος μέσα στο έγγραφο.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Δημιουργήστε ένα νέο Document and DocumentBuilder
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`DocumentBuilder` αντίρρηση για εργασία με το έγγραφο.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 2: Εισαγάγετε ένα σχήμα εικόνας
 Χρησιμοποιήστε το`InsertImage` μέθοδος του`DocumentBuilder`αντικείμενο για να εισαγάγετε ένα σχήμα εικόνας στο έγγραφο. Δώστε τη διαδρομή προς το αρχείο εικόνας ως παράμετρο.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Βήμα 3: Ανάκτηση σημείων ορίων πραγματικού σχήματος
 Πρόσβαση στο σχήμα`ShapeRenderer` χρησιμοποιώντας την`GetShapeRenderer` μέθοδος. Στη συνέχεια, ανακτήστε τα πραγματικά όρια του σχήματος σε σημεία χρησιμοποιώντας το`BoundsInPoints` ιδιοκτησία.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Παράδειγμα πηγαίου κώδικα για Λήψη σημείων ορίων πραγματικού σχήματος χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Αυτό είναι! Έχετε ανακτήσει με επιτυχία τα πραγματικά όρια ενός σχήματος σε σημεία στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.