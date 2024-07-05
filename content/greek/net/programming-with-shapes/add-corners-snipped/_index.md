---
title: Προσθήκη γωνιών που έχουν αποκοπεί
linktitle: Προσθήκη γωνιών που έχουν αποκοπεί
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να προσθέσετε ένα σχήμα με κομμένες γωνίες σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-shapes/add-corners-snipped/
---

 Αυτό το σεμινάριο εξηγεί πώς μπορείτε να προσθέσετε ένα σχήμα με κομμένες γωνίες σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Το σχήμα κομμένο στις γωνίες μπορεί να προσαρμοστεί και να εισαχθεί χρησιμοποιώντας το`InsertShape` μέθοδος.

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

## Βήμα 3: Εισαγάγετε το σχήμα κομμένο στις γωνίες
 Χρησιμοποιήστε το`InsertShape` μέθοδος του`DocumentBuilder` αντικείμενο για να εισαγάγετε ένα σχήμα με κομμένες γωνίες. Καθορίστε τον τύπο σχήματος (σε αυτήν την περίπτωση,`ShapeType.TopCornersSnipped`) και δώστε το επιθυμητό μέγεθος για το σχήμα.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Παράδειγμα πηγαίου κώδικα για Προσθήκη γωνιών που αποκόπηκαν με χρήση του Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Αυτό είναι! Προσθέσατε με επιτυχία ένα σχήμα κομμένο σε γωνίες στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.