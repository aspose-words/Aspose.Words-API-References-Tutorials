---
title: Ανίχνευση έξυπνου σχήματος τέχνης
linktitle: Ανίχνευση έξυπνου σχήματος τέχνης
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εντοπίζετε σχήματα Smart Art σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, προσδιορίζοντας γραφικές αναπαραστάσεις.
type: docs
weight: 10
url: /el/net/programming-with-shapes/detect-smart-art-shape/
---

Αυτό το σεμινάριο εξηγεί πώς να ανιχνεύσετε σχήματα Smart Art σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Τα σχήματα Smart Art είναι γραφικές αναπαραστάσεις που χρησιμοποιούνται για την οπτική παρουσίαση πληροφοριών και ιδεών.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφό σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο
 Φορτώστε το έγγραφο του Word χρησιμοποιώντας το`Document` κατασκευαστή, περνώντας τη διαδρομή προς το έγγραφο ως παράμετρο.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Βήμα 3: Ανίχνευση έξυπνων σχημάτων τέχνης
 Επαναλάβετε μέσω των θυγατρικών κόμβων του τύπου`Shape` στο έγγραφο χρησιμοποιώντας το`GetChildNodes`μέθοδος. Ελέγξτε εάν κάθε σχήμα έχει Smart Art χρησιμοποιώντας το`HasSmart Art` ιδιοκτησία.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Βήμα 4: Εξαγωγή του αποτελέσματος
Εκτυπώστε τον αριθμό των σχημάτων με το Smart Art που εντοπίστηκε στο έγγραφο.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Παράδειγμα πηγαίου κώδικα για τον εντοπισμό έξυπνου σχήματος τέχνης χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Αυτό είναι! Εντοπίσατε επιτυχώς σχήματα Smart Art στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.