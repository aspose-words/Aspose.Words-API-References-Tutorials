---
title: Κάθετη άγκυρα
linktitle: Κάθετη άγκυρα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να τοποθετείτε ένα σχήμα κατακόρυφα μέσα σε ένα έγγραφο χρησιμοποιώντας τη δυνατότητα κατακόρυφης αγκύρωσης στο Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-shapes/vertical-anchor/
---

Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε τη δυνατότητα κάθετης αγκύρωσης στο Aspose.Words για .NET για να τοποθετήσετε ένα σχήμα κατακόρυφα μέσα σε ένα έγγραφο. Ορίζοντας την ιδιότητα κατακόρυφης αγκύρωσης ενός σχήματος, μπορείτε να ελέγξετε την κατακόρυφη στοίχισή του σε σχέση με το κείμενο ή τη σελίδα.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"`με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα νέο Document και DocumentBuilder
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`DocumentBuilder` αντίρρηση για εργασία με το έγγραφο.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Εισαγάγετε και διαμορφώστε ένα σχήμα
 Εισαγάγετε ένα σχήμα στο έγγραφο χρησιμοποιώντας το`InsertShape` μέθοδος του`DocumentBuilder` αντικείμενο. Ορίστε τις επιθυμητές διαστάσεις για το σχήμα.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Βήμα 4: Ρυθμίστε την κατακόρυφη άγκυρα
Ρυθμίστε την ιδιότητα κάθετης αγκύρωσης του σχήματος για να ελέγξετε την κατακόρυφη ευθυγράμμισή του. Σε αυτό το παράδειγμα, το ρυθμίσαμε σε "Κάτω" για να αγκυρώσουμε το σχήμα στο κάτω μέρος του κειμένου ή της σελίδας.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Βήμα 5: Προσθέστε περιεχόμενο στο σχήμα
 Χρησιμοποιήστε το`MoveTo` μέθοδος του`DocumentBuilder` αντικείμενο να μετακινήσετε τον κέρσορα στην πρώτη παράγραφο του σχήματος. Στη συνέχεια, χρησιμοποιήστε το`Write` μέθοδος προσθήκης περιεχομένου στο σχήμα.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Βήμα 6: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save`μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Παράδειγμα πηγαίου κώδικα για το Vertical Anchor χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Αυτό είναι! Χρησιμοποιήσατε με επιτυχία τη δυνατότητα κάθετης αγκύρωσης στο Aspose.Words για .NET για να τοποθετήσετε ένα σχήμα κατακόρυφα μέσα σε ένα έγγραφο.