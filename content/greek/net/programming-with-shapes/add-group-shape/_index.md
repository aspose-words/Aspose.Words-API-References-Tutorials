---
title: Προσθήκη σχήματος ομάδας
linktitle: Προσθήκη σχήματος ομάδας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να προσθέσετε ένα σχήμα ομάδας με πολλά σχήματα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-shapes/add-group-shape/
---

Αυτό το σεμινάριο εξηγεί πώς να προσθέσετε ένα σχήμα ομάδας που περιέχει πολλά σχήματα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Τα σχήματα ομάδας σάς επιτρέπουν να συνδυάζετε και να χειρίζεστε πολλά σχήματα ως μια ενιαία οντότητα.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα νέο έγγραφο και σχήμα ομάδας
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και`GroupShape` αντίρρηση για εργασία με το έγγραφο.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Βήμα 3: Δημιουργήστε και προσθέστε σχήματα στο σχήμα ομάδας
 Δημιουργήστε μεμονωμένα σχήματα όπως π.χ`accentBorderShape` και`actionButtonShape` χρησιμοποιώντας την`Shape` τάξη. Προσαρμόστε τις ιδιότητές τους όπως επιθυμείτε. Προσθέστε αυτά τα σχήματα στο`groupShape` αντικείμενο.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Βήμα 4: Ορίστε τις διαστάσεις για το σχήμα ομάδας
 Ορίστε το πλάτος, το ύψος και το μέγεθος συντεταγμένων για το`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Βήμα 5: Εισαγάγετε το σχήμα ομάδας στο έγγραφο
 Δημιουργώ ένα`DocumentBuilder` αντικείμενο και εισάγετε το`groupShape` στο έγγραφο χρησιμοποιώντας το`InsertNode` μέθοδος.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Βήμα 6: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save`μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Παράδειγμα πηγαίου κώδικα για Προσθήκη σχήματος ομάδας χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Αυτό είναι! Προσθέσατε με επιτυχία ένα σχήμα ομάδας που περιέχει πολλά σχήματα στο έγγραφο του Word χρησιμοποιώντας το Aspose.W