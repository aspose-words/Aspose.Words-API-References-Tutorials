---
title: Διάταξη στο κελί
linktitle: Διάταξη στο κελί
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να σχεδιάζετε ένα σχήμα μέσα σε ένα κελί πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-shapes/layout-in-cell/
---

Αυτό το σεμινάριο εξηγεί τον τρόπο διάταξης ενός σχήματος μέσα σε ένα κελί πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Προσαρμόζοντας τις ιδιότητες σχήματος και χρησιμοποιώντας τις επιλογές διάταξης, μπορείτε να ελέγξετε τη θέση και την εμφάνιση του σχήματος μέσα στο κελί.

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

## Βήμα 3: Δημιουργήστε τον πίνακα
 Χρησιμοποιήστε το`StartTable`, `EndTable`, `InsertCell` , και`Write` μεθόδους του`DocumentBuilder` αντικείμενο να φτιάξει ένα τραπέζι. Ορίστε τον επιθυμητό κανόνα ύψους και ύψους σειράς χρησιμοποιώντας το`RowFormat` ιδιότητες.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Βήμα 4: Δημιουργήστε και μορφοποιήστε το σχήμα
 Δημιουργώ ένα`Shape` αντικείμενο και διαμορφώστε τις ιδιότητές του για να ορίσετε το υδατογράφημα. Ρυθμίστε το σχήμα που θα τοποθετηθεί σε ένα κελί χρησιμοποιώντας το`IsLayoutInCell` ιδιοκτησία.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Βήμα 5: Προσαρμόστε το σχήμα
 Προσαρμόστε την εμφάνιση και το κείμενο του σχήματος υδατογραφήματος ορίζοντας ιδιότητες όπως π.χ`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`, και τα λοιπά.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Βήμα 6: Εισαγάγετε το σχήμα στο έγγραφο
Εισαγάγετε το σχήμα του υδατογραφήματος στο έγγραφο χρησιμοποιώντας το`InsertNode` μέθοδος του`DocumentBuilder` αντικείμενο. Τοποθετήστε το σχήμα χρησιμοποιώντας το`MoveTo` μέθοδο για να το τοποθετήσετε μετά την τελευταία εκτέλεση στο έγγραφο.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Βήμα 7: Αποθηκεύστε το έγγραφο
 Αποθηκεύστε το έγγραφο στον καθορισμένο κατάλογο χρησιμοποιώντας το`Save` μέθοδος. Δώστε το επιθυμητό όνομα αρχείου με την κατάλληλη επέκταση αρχείου. Σε αυτό το παράδειγμα, αποθηκεύουμε το έγγραφο ως "WorkingWithShapes.LayoutInCell.docx".

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### Παράδειγμα πηγαίου κώδικα για Layout In Cell χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // Εμφανίστε το σχήμα έξω από το κελί του πίνακα εάν θα τοποθετηθεί σε ένα κελί.
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

Αυτό είναι! Έχετε δημιουργήσει με επιτυχία ένα σχήμα μέσα σε ένα κελί πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.