---
title: Όρια Άξονα σε Διάγραμμα
linktitle: Όρια Άξονα σε Διάγραμμα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ορίζετε τα όρια ενός άξονα σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET που ελέγχει το εύρος των τιμών που εμφανίζεται στον άξονα.
type: docs
weight: 10
url: /el/net/programming-with-charts/bounds-of-axis/
---

Αυτό το σεμινάριο εξηγεί πώς να ορίσετε τα όρια ενός άξονα σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET. Εισάγοντας ένα γράφημα, προσθέτοντας δεδομένα σειρών και διαμορφώνοντας την κλίμακα του άξονα, μπορείτε να ορίσετε τις ελάχιστες και μέγιστες τιμές για τον άξονα.

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
 Δημιουργήστε μια νέα παρουσία του`Document` τάξη και α`DocumentBuilder` αντίρρηση για εργασία με το έγγραφο.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Εισαγάγετε και διαμορφώστε ένα γράφημα
 Εισαγάγετε ένα γράφημα στο έγγραφο χρησιμοποιώντας το`InsertChart` μέθοδος του`DocumentBuilder` αντικείμενο. Ορίστε τον επιθυμητό τύπο γραφήματος και τις διαστάσεις.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Βήμα 4: Προσθήκη δεδομένων σειράς
Διαγράψτε τυχόν υπάρχουσες σειρές στο γράφημα και προσθέστε νέα δεδομένα σειρών. Σε αυτό το παράδειγμα, προσθέτουμε μια σειρά με ετικέτες "Item 1" στο "Item 5" και αντίστοιχες τιμές.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Βήμα 5: Ορίστε τα όρια του άξονα
 Διαμορφώστε την κλίμακα του άξονα Υ ορίζοντας τις ελάχιστες και μέγιστες τιμές χρησιμοποιώντας το`Scaling.Minimum` και`Scaling.Maximum` ιδιότητες του άξονα.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Βήμα 6: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Παράδειγμα πηγαίου κώδικα για Bounds Of Axis χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Αυτό είναι! Έχετε ορίσει με επιτυχία τα όρια ενός άξονα σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθατε πώς να ορίζετε τα όρια ενός άξονα σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να εισαγάγετε και να διαμορφώσετε ένα γράφημα, να προσθέσετε δεδομένα σειράς και να ορίσετε τις ελάχιστες και μέγιστες τιμές για την κλίμακα του άξονα. Το Aspose.Words για .NET παρέχει ένα ισχυρό και ευέλικτο API για επεξεργασία λέξεων με έγγραφα Word, επιτρέποντάς σας να δημιουργείτε εύκολα δυναμικά και οπτικά ελκυστικά γραφήματα.


### Συχνές ερωτήσεις

#### Q1. Τι είναι το Aspose.Words για .NET;
Το Aspose.Words για .NET είναι μια βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με έγγραφα του Word μέσω προγραμματισμού. Παρέχει ένα ευρύ φάσμα δυνατοτήτων και λειτουργιών για τη δημιουργία, το χειρισμό και την αποθήκευση εγγράφων του Word.

#### Ε2. Πώς μπορώ να εγκαταστήσω το Aspose.Words για .NET;
Για να εγκαταστήσετε το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε τη Διαχείριση πακέτων NuGet στο Visual Studio. Απλώς αναζητήστε το "Aspose.Words" στον διαχειριστή πακέτων NuGet και εγκαταστήστε το στο έργο σας.

#### Ε3. Μπορώ να χρησιμοποιήσω το Aspose.Words για .NET με άλλες γλώσσες προγραμματισμού;
Όχι, το Aspose.Words για .NET έχει σχεδιαστεί ειδικά για εφαρμογές .NET. Λειτουργεί με γλώσσες προγραμματισμού όπως C# και VB.NET.

#### Q4. Υπάρχουν άλλες προϋποθέσεις για τη χρήση του Aspose.Words για .NET;
Εκτός από την εγκατάσταση της βιβλιοθήκης Aspose.Words για .NET, θα πρέπει να έχετε βασικές γνώσεις προγραμματισμού C# και επεξεργασίας λέξεων με έγγραφα του Word. Η εξοικείωση με το πλαίσιο .NET θα είναι επίσης χρήσιμη.