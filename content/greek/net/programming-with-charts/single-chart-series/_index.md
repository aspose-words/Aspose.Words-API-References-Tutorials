---
title: Προσαρμόστε τη σειρά μεμονωμένων γραφημάτων σε ένα γράφημα
linktitle: Προσαρμόστε τη σειρά μεμονωμένων γραφημάτων σε ένα γράφημα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσαρμόζετε μεμονωμένες σειρές γραφημάτων σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-charts/single-chart-series/
---

Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να προσαρμόσετε μεμονωμένες σειρές γραφημάτων σε ένα γράφημα. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς μπορείτε να δημιουργήσετε ένα γράφημα, να αποκτήσετε πρόσβαση σε συγκεκριμένες σειρές και να τροποποιήσετε τις ιδιότητές τους.

## Βήμα 1: Ρύθμιση του έργου

Βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET. Μπορείτε να το κατεβάσετε χρησιμοποιώντας τη Διαχείριση πακέτων NuGet για να το εγκαταστήσετε.
- Μια διαδρομή καταλόγου εγγράφων όπου θα αποθηκευτεί το έγγραφο εξόδου.

## Βήμα 2: Δημιουργήστε ένα νέο έγγραφο και εισαγάγετε ένα γράφημα.

 Δημιούργησε ένα νέο`Document` αντικείμενο και α`DocumentBuilder` για τη δημιουργία του εγγράφου.

```csharp
// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Στη συνέχεια, χρησιμοποιήστε το`InsertChart` μέθοδος του`DocumentBuilder` για να εισαγάγετε ένα γραμμικό γράφημα στο έγγραφο.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Βήμα 3: Πρόσβαση και προσαρμογή σειρών γραφημάτων

 Για να τροποποιήσετε μεμονωμένες σειρές γραφημάτων, πρέπει να αποκτήσετε πρόσβαση στο`ChartSeries` αντικείμενα του διαγράμματος.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Βήμα 4: Αποθηκεύστε το έγγραφο

 Τέλος, αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος του`Document` αντικείμενο.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Αυτό ολοκληρώνει την εφαρμογή της προσαρμογής μιας μεμονωμένης σειράς γραφημάτων χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για σειρά μεμονωμένων γραφημάτων χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Μπορείτε επίσης να καθορίσετε εάν η γραμμή που συνδέει τα σημεία του γραφήματος θα εξομαλυνθεί χρησιμοποιώντας splines Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Καθορίζει εάν από προεπιλογή το γονικό στοιχείο θα αντιστρέφει τα χρώματά του εάν η τιμή είναι αρνητική.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## συμπέρασμα

Σε αυτό το σεμινάριο, έχετε μάθει πώς να προσαρμόζετε μια μεμονωμένη σειρά γραφημάτων σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα, μπορείτε να δημιουργήσετε ένα νέο έγγραφο, να εισαγάγετε ένα γράφημα γραμμής, να αποκτήσετε πρόσβαση σε συγκεκριμένες σειρές γραφημάτων και να τροποποιήσετε τις ιδιότητές τους για να επιτύχετε την επιθυμητή προσαρμογή.

Το Aspose.Words για .NET παρέχει ισχυρές δυνατότητες χειρισμού γραφημάτων σε έγγραφα του Word. Με την πρόσβαση σε μεμονωμένες σειρές γραφημάτων, μπορείτε να εφαρμόσετε συγκεκριμένες τροποποιήσεις για να προσαρμόσετε την εμφάνιση και τη συμπεριφορά τους. Αυτό σας επιτρέπει να αλλάξετε το όνομα της σειράς, να ενεργοποιήσετε την εξομάλυνση της γραμμής του γραφήματος, να προσαρμόσετε δείκτες για σημεία δεδομένων, να αντιστρέψετε χρώματα για αρνητικές τιμές και πολλά άλλα, για να βελτιώσετε την οπτική αναπαράσταση του γραφήματος σας.

Η προσαρμογή μιας μεμονωμένης σειράς γραφημάτων σάς παρέχει την ευελιξία να επισημάνετε συγκεκριμένα δεδομένα ή να τονίσετε συγκεκριμένες τάσεις μέσα στο γράφημά σας. Με το Aspose.Words για .NET, μπορείτε εύκολα να αποκτήσετε πρόσβαση και να τροποποιήσετε τις ιδιότητες της σειράς γραφημάτων, επιτρέποντάς σας να δημιουργήσετε οπτικά ελκυστικά και ενημερωτικά γραφήματα στα έγγραφα του Word.

### Συχνές ερωτήσεις

#### Q1. Μπορώ να προσαρμόσω πολλές σειρές γραφημάτων σε ένα γράφημα;
 Ναι, μπορείτε να προσαρμόσετε πολλές σειρές γραφημάτων σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET. Με την πρόσβαση στο`ChartSeries`αντικείμενα εντός του γραφήματος, μπορείτε να επιλέξετε και να τροποποιήσετε πολλές σειρές με βάση τους δείκτες τους ή συγκεκριμένα κριτήρια. Χρησιμοποιήστε έναν βρόχο ή μεμονωμένες αναθέσεις για να τροποποιήσετε τις επιθυμητές ιδιότητες για κάθε σειρά γραφημάτων. Με αυτόν τον τρόπο, μπορείτε να εφαρμόσετε διαφορετικές προσαρμογές σε πολλές σειρές μέσα στο ίδιο γράφημα.

#### Ε2. Πώς μπορώ να αλλάξω το όνομα μιας σειράς γραφημάτων;
 Για να αλλάξετε το όνομα μιας σειράς γραφημάτων σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET, πρέπει να αποκτήσετε πρόσβαση στο`Name` ιδιοκτησία του`ChartSeries` αντικείμενο και ορίστε το στο επιθυμητό όνομα. Το όνομα της σειράς εμφανίζεται συνήθως στο υπόμνημα του γραφήματος ή στις ετικέτες δεδομένων, παρέχοντας μια περιγραφική ετικέτα για τη σειρά. Τροποποιώντας το όνομα της σειράς, μπορείτε να παρέχετε ουσιαστικά ονόματα που αντικατοπτρίζουν τα δεδομένα που αντιπροσωπεύονται από κάθε σειρά.

#### Ε3. Τι είναι η εξομάλυνση σειρών γραφημάτων;
Η εξομάλυνση της σειράς γραφημάτων είναι μια τεχνική οπτικής βελτίωσης που σας επιτρέπει να δημιουργήσετε μια ομαλή γραμμή που συνδέει τα σημεία στο γράφημα. Εφαρμόζει έναν αλγόριθμο εξομάλυνσης, όπως οι splines Catmull-Rom, για παρεμβολή μεταξύ σημείων δεδομένων και δημιουργία μιας οπτικά ευχάριστης καμπύλης. Για να ενεργοποιήσετε την εξομάλυνση σειρών σε ένα γράφημα χρησιμοποιώντας το Aspose.Words για .NET, μεταβείτε στο`Smooth` ιδιοκτησία του`ChartSeries` αντικείμενο και ρυθμίστε το σε`true`. Η εξομάλυνση μπορεί να είναι χρήσιμη για την εμφάνιση τάσεων ή μοτίβων σε δεδομένα με ακανόνιστες διακυμάνσεις.

#### Ε4. Πώς μπορώ να προσαρμόσω δείκτες για σημεία δεδομένων σε μια σειρά γραφημάτων;
 Για να προσαρμόσετε δείκτες για σημεία δεδομένων σε μια σειρά γραφημάτων χρησιμοποιώντας το Aspose.Words για .NET, πρέπει να αποκτήσετε πρόσβαση στο`Marker` ιδιοκτησία του`ChartSeries` αντικείμενο και να τροποποιήσει τις ιδιότητές του όπως`Symbol` και`Size`. Οι δείκτες είναι οπτικοί δείκτες που τοποθετούνται στο γράφημα για να αντιπροσωπεύουν μεμονωμένα σημεία δεδομένων. Μπορείτε να επιλέξετε από μια ποικιλία ενσωματωμένων συμβόλων δεικτών και να προσαρμόσετε το μέγεθός τους για να επισημάνετε ή να διαφοροποιήσετε συγκεκριμένα σημεία δεδομένων στη σειρά.

#### Q5. Μπορώ να αντιστρέψω χρώματα για αρνητικές τιμές σε μια σειρά γραφημάτων;
 Ναι, μπορείτε να αντιστρέψετε χρώματα για αρνητικές τιμές σε μια σειρά γραφημάτων χρησιμοποιώντας το Aspose.Words για .NET. Ρυθμίζοντας το`InvertIfNegative` ιδιοκτησία του`ChartSeries` αντιτίθεμαι`true`, τα χρώματα για σημεία δεδομένων με αρνητικές τιμές θα αντιστραφούν, καθιστώντας τα οπτικά διακριτά από τις θετικές τιμές. Αυτή η δυνατότητα μπορεί να είναι χρήσιμη κατά τη σύγκριση θετικών και αρνητικών τιμών σε μια σειρά γραφημάτων, παρέχοντας σαφή διαφοροποίηση μεταξύ των δύο.