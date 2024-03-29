---
title: Δημιουργία και προσαρμογή γραφήματος χρησιμοποιώντας σχήμα
linktitle: Δημιουργία και προσαρμογή γραφήματος χρησιμοποιώντας σχήμα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε και να προσαρμόζετε ένα γράφημα χρησιμοποιώντας ένα σχήμα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-charts/create-chart-using-shape/
---

Αυτό το σεμινάριο εξηγεί πώς να δημιουργήσετε ένα γράφημα χρησιμοποιώντας ένα σχήμα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.

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

## Βήμα 3: Εισαγάγετε και διαμορφώστε ένα σχήμα γραφήματος
 Εισαγάγετε ένα σχήμα γραφήματος στο έγγραφο χρησιμοποιώντας το`InsertChart` μέθοδος του`DocumentBuilder` αντικείμενο. Ορίστε τον επιθυμητό τύπο γραφήματος και τις διαστάσεις.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Βήμα 4: Προσαρμόστε το γράφημα
Προσαρμόστε το γράφημα τροποποιώντας διάφορες ιδιότητες, όπως τον τίτλο του γραφήματος και το υπόμνημα.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Βήμα 5: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Παράδειγμα πηγαίου κώδικα για Δημιουργία γραφήματος με χρήση σχήματος χρησιμοποιώντας το Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Λάβετε υπόψη ότι εάν η τιμή null ή κενή έχει καθοριστεί ως κείμενο τίτλου, ο τίτλος που δημιουργείται αυτόματα θα εμφανιστεί.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Αυτό είναι! Έχετε δημιουργήσει με επιτυχία ένα γράφημα χρησιμοποιώντας ένα σχήμα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.

## συμπέρασμα
Σε αυτό το σεμινάριο, έχετε μάθει πώς να δημιουργείτε ένα γράφημα χρησιμοποιώντας ένα σχήμα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να εισαγάγετε και να διαμορφώσετε ένα σχήμα γραφήματος, να προσαρμόσετε την εμφάνισή του και να αποθηκεύσετε το έγγραφο. Το Aspose.Words για .NET παρέχει ένα ολοκληρωμένο σύνολο δυνατοτήτων για την επεξεργασία λέξεων με έγγραφα και γραφήματα του Word, επιτρέποντάς σας να δημιουργείτε γραφήματα με επαγγελματική εμφάνιση και οπτικά ελκυστικά απευθείας στις εφαρμογές σας .NET.

### Συχνές ερωτήσεις

#### Q1. Μπορώ να δημιουργήσω γραφήματα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;
Ναι, με το Aspose.Words για .NET, μπορείτε να δημιουργήσετε γραφήματα σε ένα έγγραφο του Word μέσω προγραμματισμού. Το Aspose.Words παρέχει API και λειτουργίες για την εισαγωγή διαφόρων τύπων γραφημάτων, την προσαρμογή της εμφάνισής τους και τον χειρισμό δεδομένων γραφημάτων.

#### Ε2. Ποιοι τύποι γραφημάτων υποστηρίζονται από το Aspose.Words για .NET;
Το Aspose.Words για .NET υποστηρίζει ένα ευρύ φάσμα τύπων γραφημάτων, συμπεριλαμβανομένων γραμμικών γραφημάτων, γραφημάτων ράβδων, γραφημάτων πίτας, γραφημάτων περιοχής, διαγραμμάτων διασποράς και άλλων. Μπορείτε να επιλέξετε τον κατάλληλο τύπο γραφήματος με βάση τα δεδομένα σας και τις απαιτήσεις οπτικοποίησης.

#### Ε3. Μπορώ να προσαρμόσω την εμφάνιση του δημιουργημένου γραφήματος;
Ναι, μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος που δημιουργήθηκε χρησιμοποιώντας το Aspose.Words για .NET. Μπορείτε να τροποποιήσετε ιδιότητες όπως τίτλο γραφήματος, θέση υπομνήματος, ετικέτες δεδομένων, ετικέτες αξόνων, χρώματα και άλλα οπτικά στοιχεία για να καλύψετε τις συγκεκριμένες ανάγκες σχεδίασης και μορφοποίησης.
