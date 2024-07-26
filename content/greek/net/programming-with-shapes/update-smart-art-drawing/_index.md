---
title: Ενημερώστε το Έξυπνο Σχέδιο Τέχνης
linktitle: Ενημερώστε το Έξυπνο Σχέδιο Τέχνης
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ενημερώνετε το σχέδιο Smart Art σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-shapes/update-smart-art-drawing/
---

Αυτό το σεμινάριο εξηγεί πώς να ενημερώσετε το σχέδιο Smart Art σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Επαναλαμβάνοντας τα σχήματα του εγγράφου και ελέγχοντας εάν διαθέτουν Smart Art, μπορείτε να ενημερώσετε το σχέδιο Smart Art ώστε να αντικατοπτρίζει τυχόν αλλαγές που έγιναν στα δεδομένα του.

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
 Φορτώστε το έγγραφο του Word που περιέχει το σχέδιο Smart Art χρησιμοποιώντας το`Document` κατασκευαστής τάξης.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Βήμα 3: Ενημερώστε το Έξυπνο Καλλιτεχνικό Σχέδιο
 Επαναλάβετε τα σχήματα στο έγγραφο χρησιμοποιώντας το`GetChildNodes` μέθοδος με το`NodeType.Shape` παράμετρος. Ελέγξτε εάν κάθε σχήμα έχει Smart Art χρησιμοποιώντας το`HasSmartArt`ιδιοκτησίας, και αν αληθεύει, καλέστε το`UpdateSmartArtDrawing` μέθοδος ενημέρωσης του σχεδίου Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Παράδειγμα πηγαίου κώδικα για Ενημέρωση έξυπνου σχεδίου τέχνης χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Αυτό είναι! Ενημερώσατε με επιτυχία το σχέδιο Smart Art στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.