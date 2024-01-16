---
title: Εφαρμόστε περιγράμματα και σκίαση στην παράγραφο στο έγγραφο του Word
linktitle: Εφαρμόστε περιγράμματα και σκίαση στην παράγραφο στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εφαρμόζετε περιγράμματα και σκίαση σε μια παράγραφο σε έγγραφο word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
Σε αυτό το σεμινάριο, θα σας δείξουμε πώς να εφαρμόζετε περιγράμματα και σκίαση σε μια παράγραφο σε έγγραφο word χρησιμοποιώντας τη λειτουργικότητα του Aspose.Words για .NET. Ακολουθήστε τα παρακάτω βήματα για να κατανοήσετε τον πηγαίο κώδικα και να εφαρμόσετε αλλαγές μορφοποίησης.

## Βήμα 1: Δημιουργία και διαμόρφωση του εγγράφου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έγγραφο και ένα σχετικό αντικείμενο DocumentBuilder. Δείτε πώς:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 2: Διαμόρφωση περιγράμματος

Τώρα ας διαμορφώσουμε τα περιγράμματα της παραγράφου καθορίζοντας το στυλ περιγράμματος για κάθε πλευρά. Δείτε πώς:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Βήμα 3: Ρύθμιση συμπλήρωσης

Τώρα θα διαμορφώσουμε το γέμισμα παραγράφου καθορίζοντας την υφή και τα χρώματα γεμίσματος. Δείτε πώς:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Βήμα 4: Προσθέστε περιεχόμενο

Θα προσθέσουμε κάποιο μορφοποιημένο περιεχόμενο στην παράγραφο. Δείτε πώς:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Βήμα 3: Αποθήκευση του εγγράφου

 Αφού εισαγάγετε το πεδίο φόρμας εισαγωγής κειμένου, αποθηκεύστε το έγγραφο στην επιθυμητή θέση χρησιμοποιώντας το`Save` μέθοδος. Φροντίστε να παρέχετε την κατάλληλη διαδρομή αρχείου:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Παράδειγμα πηγαίου κώδικα για Εφαρμογή περιγραμμάτων και σκίασης στην παράγραφο χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δυνατότητα Εφαρμογή περιγραμμάτων και σκίασης στην παράγραφο με το Aspose.Words για .NET:

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να εφαρμόζουμε περιγράμματα και σκίαση σε μια παράγραφο σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Διαμορφώνοντας τις παραγράφους`Borders` και`Shading` ιδιότητες, μπορέσαμε να ορίσουμε το στυλ περιγράμματος, το χρώμα γραμμής και το χρώμα πλήρωσης για την παράγραφο. Το Aspose.Words για .NET παρέχει ισχυρές δυνατότητες μορφοποίησης για την προσαρμογή της εμφάνισης των παραγράφων και τη βελτίωση της οπτικής αναπαράστασης των εγγράφων σας.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να εφαρμόσω περιγράμματα και σκίαση σε μια παράγραφο σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

Α: Για να εφαρμόσετε περιγράμματα και σκίαση σε μια παράγραφο σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, ακολουθήστε τα εξής βήματα:
1.  Δημιουργήστε ένα νέο έγγραφο και α`DocumentBuilder` αντικείμενο.
2.  Διαμορφώστε τα περιγράμματα της παραγράφου με πρόσβαση στο`Borders` ιδιοκτησία του`ParagraphFormat` και ορίζοντας το στυλ περιγράμματος για κάθε πλευρά.
3.  Διαμορφώστε το γέμισμα παραγράφου, μεταβαίνοντας στο`Shading` ιδιοκτησία του`ParagraphFormat` και προσδιορίζοντας την υφή και τα χρώματα γεμίσματος.
4.  Προσθέστε περιεχόμενο στην παράγραφο χρησιμοποιώντας το`Write` μέθοδος του`DocumentBuilder`.
5.  Αποθηκεύστε το έγγραφο χρησιμοποιώντας το`Save` μέθοδος.

#### Ε: Πώς ορίζω το στυλ περιγράμματος για κάθε πλευρά της παραγράφου;

 Α: Για να ορίσετε το στυλ περιγράμματος για κάθε πλευρά της παραγράφου, μπορείτε να αποκτήσετε πρόσβαση στο`Borders` ιδιοκτησία του`ParagraphFormat` και ρυθμίστε το`LineStyle` ιδιοκτησία για το καθένα`BorderType` (π.χ,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Μπορείτε να καθορίσετε διαφορετικά στυλ γραμμής όπως π.χ`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, και τα λοιπά.

#### Ε: Πώς μπορώ να καθορίσω την υφή και τα χρώματα γεμίσματος για τη σκίαση της παραγράφου;

 Α: Για να καθορίσετε την υφή και τα χρώματα γεμίσματος για τη σκίαση της παραγράφου, μπορείτε να αποκτήσετε πρόσβαση στο`Shading` ιδιοκτησία του`ParagraphFormat` και ρυθμίστε το`Texture` ιδιότητα σε έναν επιθυμητό δείκτη υφής (π.χ.`TextureIndex.TextureDiagonalCross` ). Μπορείτε επίσης να ρυθμίσετε το`BackgroundPatternColor` και`ForegroundPatternColor` ιδιότητες στα επιθυμητά χρώματα χρησιμοποιώντας το`System.Drawing.Color` τάξη.