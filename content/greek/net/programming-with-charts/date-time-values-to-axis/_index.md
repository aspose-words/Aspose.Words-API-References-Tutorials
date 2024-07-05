---
title: Προσθέστε τιμές ημερομηνίας ώρας στον άξονα ενός γραφήματος
linktitle: Προσθέστε τιμές ημερομηνίας ώρας στον άξονα ενός γραφήματος
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσθέτετε τιμές ημερομηνίας ώρας στον άξονα ενός γραφήματος χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-charts/date-time-values-to-axis/
---

Αυτό το σεμινάριο εξηγεί πώς μπορείτε να προσθέσετε τιμές ημερομηνίας ώρας στον άξονα ενός γραφήματος χρησιμοποιώντας το Aspose.Words για .NET.

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

## Βήμα 3: Εισαγάγετε και διαμορφώστε ένα σχήμα γραφήματος
 Εισαγάγετε ένα σχήμα γραφήματος στο έγγραφο χρησιμοποιώντας το`InsertChart` μέθοδος του`DocumentBuilder` αντικείμενο. Ορίστε τον επιθυμητό τύπο γραφήματος και τις διαστάσεις.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Βήμα 4: Προσθήκη δεδομένων στο γράφημα
Προσθέστε δεδομένα στη σειρά γραφημάτων, συμπεριλαμβανομένων των τιμών ημερομηνίας ώρας.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Βήμα 5: Διαμορφώστε τον Άξονα
Διαμορφώστε τον άξονα Χ του γραφήματος για να εμφανίζει τις τιμές ημερομηνίας ώρας.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Βήμα 6: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Παράδειγμα πηγαίου κώδικα για Date Time Values to Axis χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Ορίστε τις κύριες μονάδες σε μια εβδομάδα και τις δευτερεύουσες σε μια ημέρα.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Αυτό το παράδειγμα κώδικα δημιουργεί ένα νέο έγγραφο του Word, εισάγει ένα γράφημα στηλών με τιμές ημερομηνίας ώρας στον άξονα X και αποθηκεύει το έγγραφο στον καθορισμένο κατάλογο.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθατε πώς να προσθέτετε τιμές ημερομηνίας ώρας στον άξονα ενός γραφήματος χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να δημιουργήσετε ένα γράφημα, να προσθέσετε τιμές ημερομηνίας ώρας στη σειρά και να διαμορφώσετε τον άξονα ώστε να εμφανίζει με ακρίβεια τις τιμές ημερομηνίας ώρας. Το Aspose.Words για .NET παρέχει ένα ισχυρό σύνολο δυνατοτήτων για επεξεργασία λέξεων με γραφήματα σε έγγραφα του Word, επιτρέποντάς σας να αναπαραστήσετε και να οπτικοποιήσετε αποτελεσματικά δεδομένα με τιμές ημερομηνίας.

### Συχνές ερωτήσεις

#### Q1. Μπορώ να προσθέσω τιμές ημερομηνίας ώρας στον άξονα ενός γραφήματος χρησιμοποιώντας το Aspose.Words για .NET;
Ναι, με το Aspose.Words για .NET, μπορείτε να προσθέσετε και να εμφανίσετε τιμές ημερομηνίας ώρας στον άξονα ενός γραφήματος σε ένα έγγραφο του Word. Το Aspose.Words παρέχει API και λειτουργίες για εργασία με διάφορους τύπους γραφημάτων και προσαρμογή της εμφάνισής τους, συμπεριλαμβανομένου του χειρισμού τιμών ημερομηνίας ώρας στον άξονα.

#### Ε2. Πώς μπορώ να προσθέσω τιμές ημερομηνίας ώρας στη σειρά γραφημάτων;
 Για να προσθέσετε τιμές ημερομηνίας ώρας στη σειρά γραφημάτων, μπορείτε να χρησιμοποιήσετε το`Add`μέθοδος της σειράς του γραφήματος. Δώστε μια σειρά από τιμές ημερομηνίας ώρας ως δεδομένα κατηγορίας (άξονας Χ), μαζί με τις αντίστοιχες τιμές σειράς. Αυτό σας επιτρέπει να σχεδιάσετε σημεία δεδομένων με τιμές ημερομηνίας ώρας στο γράφημα.

#### Ε3. Πώς μπορώ να διαμορφώσω τον άξονα ώστε να εμφανίζει τιμές ημερομηνίας ώρας;
 Μπορείτε να διαμορφώσετε τον άξονα του γραφήματος ώστε να εμφανίζει τιμές ημερομηνίας ώρας ορίζοντας τις κατάλληλες ιδιότητες. Για παράδειγμα, μπορείτε να καθορίσετε τις ελάχιστες και μέγιστες τιμές για τον άξονα χρησιμοποιώντας το`Scaling.Minimum` και`Scaling.Maximum` ιδιότητες, αντίστοιχα. Επιπλέον, μπορείτε να ορίσετε τις κύριες και δευτερεύουσες μονάδες για να ορίσετε το διάστημα και να σημειώσετε σημάδια για τον άξονα.
