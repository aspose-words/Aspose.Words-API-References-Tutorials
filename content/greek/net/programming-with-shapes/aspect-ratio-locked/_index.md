---
title: Κλειδωμένος λόγος διαστάσεων
linktitle: Κλειδωμένος λόγος διαστάσεων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να κλειδώνετε ή να ξεκλειδώνετε την αναλογία διαστάσεων ενός σχήματος σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-shapes/aspect-ratio-locked/
---

Αυτό το σεμινάριο εξηγεί πώς να κλειδώσετε ή να ξεκλειδώσετε την αναλογία διαστάσεων ενός σχήματος σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Κλειδώνοντας την αναλογία διαστάσεων, μπορείτε να διατηρήσετε τις αρχικές αναλογίες του σχήματος όταν αλλάζετε το μέγεθός του.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα νέο Document και DocumentBuilder
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`DocumentBuilder`αντίρρηση για εργασία με το έγγραφο.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Εισαγάγετε ένα σχήμα εικόνας
 Χρησιμοποιήστε το`InsertImage` μέθοδος του`DocumentBuilder` αντικείμενο για να εισαγάγετε ένα σχήμα εικόνας στο έγγραφο. Δώστε τη διαδρομή προς το αρχείο εικόνας ως παράμετρο.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Βήμα 4: Κλείδωμα ή ξεκλείδωμα της αναλογίας διαστάσεων
 Ρυθμίστε το`AspectRatioLocked` ιδιότητα του σχήματος να`true` ή`false` για να κλειδώσετε ή να ξεκλειδώσετε την αναλογία διαστάσεων, αντίστοιχα.

```csharp
shape.AspectRatioLocked = false; //Ξεκλειδώστε την αναλογία διαστάσεων
```

## Βήμα 5: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Παράδειγμα πηγαίου κώδικα για Αναλογία Διαστάσεων Κλειδωμένο με χρήση Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Αυτό είναι! Έχετε κλειδώσει ή ξεκλειδώσει με επιτυχία την αναλογία διαστάσεων ενός σχήματος στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.