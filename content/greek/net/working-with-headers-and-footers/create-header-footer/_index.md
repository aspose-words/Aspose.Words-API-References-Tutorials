---
title: Δημιουργία υποσέλιδου κεφαλίδας
linktitle: Δημιουργία υποσέλιδου κεφαλίδας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε κεφαλίδες και υποσέλιδα στα έγγραφα του Word με το Aspose.Words για .NET. Προσαρμόστε τις κεφαλίδες και τα υποσέλιδα για κάθε σελίδα.
type: docs
weight: 10
url: /el/net/working-with-headers-and-footers/create-header-footer/
---

Ακολουθεί ένας οδηγός βήμα προς βήμα για να εξηγήσετε τον ακόλουθο πηγαίο κώδικα C# για τη δημιουργία κεφαλίδων και υποσέλιδων χρησιμοποιώντας τη λειτουργικότητα Aspose.Words για .NET. Βεβαιωθείτε ότι έχετε συμπεριλάβει τη βιβλιοθήκη Aspose.Words στο έργο σας πριν χρησιμοποιήσετε αυτόν τον κώδικα.

## Βήμα 1: Ορισμός διαδρομής καταλόγου εγγράφων

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς τον κατάλογο των εγγράφων σας όπου θα αποθηκευτεί το επεξεργασμένο έγγραφο.

## Βήμα 2: Δημιουργήστε ένα έγγραφο και μια δημιουργία εγγράφων

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Εδώ δημιουργούμε ένα παράδειγμα του`Document` τάξη και ένα παράδειγμα του`DocumentBuilder` class που θα μας επιτρέψει να χειριστούμε το έγγραφο και να προσθέσουμε στοιχεία.

## Βήμα 3: Ορίστε τις παραμέτρους σελίδας και την πρώτη κεφαλίδα

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Καθορίστε αν θέλουμε οι κεφαλίδες/υποσέλιδα της πρώτης σελίδας να διαφέρουν από τις άλλες σελίδες.
// Μπορείτε επίσης να χρησιμοποιήσετε την ιδιότητα PageSetup.OddAndEvenPagesHeaderFooter για να καθορίσετε
// διαφορετικές κεφαλίδες/υποσέλιδα για μονές και ζυγές σελίδες.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Ορίζουμε τις παραμέτρους της σελίδας, συμπεριλαμβανομένης της απόστασης κεφαλίδας, και μετά μετακινούμαστε στην κύρια κεφαλίδα (`HeaderPrimary`). Χρησιμοποιούμε τη δημιουργία εγγράφων για να προσθέσουμε κείμενο και να μορφοποιήσουμε την κεφαλίδα.

## Βήμα 4: Εισαγάγετε μια εικόνα και ένα κείμενο στην κύρια κεφαλίδα

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Χρησιμοποιούμε τη δημιουργία εγγράφων για να εισαγάγουμε μια εικόνα στην επάνω αριστερή γωνία της κύριας κεφαλίδας και, στη συνέχεια, προσθέτουμε κείμενο με δεξιά στοίχιση.

## Βήμα 5: Εισαγάγετε έναν πίνακα στο κύριο υποσέλιδο

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## Βήμα 6: Προσθέστε μια νέα σελίδα και ορίστε κεφαλίδες/υποσέλιδα

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Αυτή η ενότητα δεν χρειάζεται διαφορετική κεφαλίδα/υποσέλιδο για την πρώτη σελίδα, χρειαζόμαστε μόνο μία σελίδα τίτλου στο έγγραφο,
//και η κεφαλίδα/υποσέλιδο για αυτήν τη σελίδα έχει ήδη οριστεί στην προηγούμενη ενότητα.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Αυτή η ενότητα εμφανίζει τις κεφαλίδες/υποσέλιδα της προηγούμενης ενότητας από προεπιλογή, καλέστε το currentSection.HeadersFooters.LinkToPrevious(false) για να σπάσετε αυτόν τον σύνδεσμο,
// το πλάτος της σελίδας είναι διαφορετικό για τη νέα ενότητα, επομένως πρέπει να ορίσουμε διαφορετικά πλάτη κελιών για έναν πίνακα υποσέλιδου.
currentSection.HeadersFooters.LinkToPrevious(false);

// Εάν θέλουμε να χρησιμοποιήσουμε τις ήδη υπάρχουσες κεφαλίδες/υποσέλιδα για αυτήν την ενότητα,
//αλλά με μερικές μικρές αλλαγές, ίσως είναι λογικό να αντιγράψετε τις κεφαλίδες/υποσέλιδα
// από την προηγούμενη ενότητα και εφαρμόζουμε τις απαραίτητες αλλαγές όπου τις θέλουμε.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Αποθηκεύστε το έγγραφο
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Προσθέτουμε μια αλλαγή σελίδας και μια αλλαγή ενότητας για να δημιουργήσουμε μια νέα σελίδα όπου θα είναι ορατές οι κύριες κεφαλίδες/υποσέλιδα. Ορίζουμε τις παραμέτρους για τη νέα ενότητα και, στη συνέχεια, χρησιμοποιούμε το`CopyHeadersFootersFromPreviousSection` μέθοδος για την αντιγραφή των κεφαλίδων/υποσέλιδων από την προηγούμενη ενότητα. Τέλος, ορίζουμε τα κατάλληλα πλάτη κελιών για τον κύριο πίνακα υποσέλιδου και αποθηκεύουμε το έγγραφο.

### Παράδειγμα πηγαίου κώδικα για τη δημιουργία κεφαλίδων και υποσέλιδων με το Aspose.Words για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Καθορίστε εάν θέλουμε οι κεφαλίδες/υποσέλιδα της πρώτης σελίδας να διαφέρουν από άλλες σελίδες.
// Μπορείτε επίσης να χρησιμοποιήσετε την ιδιότητα PageSetup.OddAndEvenPagesHeaderFooter για να καθορίσετε
// διαφορετικές κεφαλίδες/υποσέλιδα για μονές και ζυγές σελίδες.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Εισαγάγετε μια τοποθετημένη εικόνα στην επάνω/αριστερή γωνία της κεφαλίδας.
// Η απόσταση από το επάνω/αριστερό άκρο της σελίδας έχει οριστεί σε 10 σημεία.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Χρησιμοποιούμε έναν πίνακα με δύο κελιά για να δημιουργήσουμε ένα μέρος του κειμένου στη γραμμή (με αρίθμηση σελίδας).
// Να ευθυγραμμιστεί αριστερά και το άλλο μέρος του κειμένου (με πνευματικά δικαιώματα) να ευθυγραμμιστεί δεξιά.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Χρησιμοποιεί τα πεδία PAGE και NUMPAGES για να υπολογίσει αυτόματα τον τρέχοντα αριθμό σελίδας και πολλές σελίδες.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// Κάντε μια αλλαγή σελίδας για να δημιουργήσετε μια δεύτερη σελίδα στην οποία θα εμφανίζονται οι κύριες κεφαλίδες/υποσέλιδα.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Αυτή η ενότητα δεν χρειάζεται διαφορετική κεφαλίδα/υποσέλιδο πρώτης σελίδας, χρειαζόμαστε μόνο μία σελίδα τίτλου στο έγγραφο,
//και η κεφαλίδα/υποσέλιδο για αυτήν τη σελίδα έχει ήδη οριστεί στην προηγούμενη ενότητα.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Αυτή η ενότητα εμφανίζει κεφαλίδες/υποσέλιδα από την προηγούμενη ενότητα
// από προεπιλογή καλέστε το currentSection.HeadersFooters.LinkToPrevious(false) για να ακυρώσετε αυτό το πλάτος σελίδας
// είναι διαφορετικό για τη νέα ενότητα και επομένως πρέπει να ορίσουμε διαφορετικά πλάτη κελιών για έναν πίνακα υποσέλιδου.
currentSection.HeadersFooters.LinkToPrevious(false);

// Αν θέλουμε να χρησιμοποιήσουμε το ήδη υπάρχον σύνολο κεφαλίδας/υποσέλιδου για αυτήν την ενότητα.
// Αλλά με κάποιες μικρές τροποποιήσεις, τότε μπορεί να είναι σκόπιμο να αντιγράψετε κεφαλίδες/υποσέλιδα
// από την προηγούμενη ενότητα και εφαρμόζουμε τις απαραίτητες τροποποιήσεις όπου τις θέλουμε.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να προσθέσω μια κεφαλίδα στο έγγραφό μου στο Aspose.Words;

 Α: Για να προσθέσετε μια κεφαλίδα στο έγγραφό σας στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` μέθοδος. Αυτή η μέθοδος προσθέτει μια κύρια επικεφαλίδα στην πρώτη ενότητα του εγγράφου σας.

#### Ε: Πώς μπορώ να προσθέσω ένα υποσέλιδο στο έγγραφό μου στο Aspose.Words;

 Α: Για να προσθέσετε ένα υποσέλιδο στο έγγραφό σας στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`μέθοδος. Αυτή η μέθοδος προσθέτει ένα κύριο υποσέλιδο στην πρώτη ενότητα του εγγράφου σας.

#### Ε: Πώς μπορώ να προσθέσω κείμενο στην κεφαλίδα ή το υποσέλιδο μου στο Aspose.Words;

 Α: Για να προσθέσετε κείμενο στην κεφαλίδα ή το υποσέλιδο σας στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`HeaderFooter.Paragraphs` ιδιότητα για να λάβετε τη συλλογή παραγράφων της κεφαλίδας ή του υποσέλιδου και, στη συνέχεια, προσθέστε μια παράγραφο που περιέχει το κείμενό σας σε αυτήν τη συλλογή χρησιμοποιώντας το`ParagraphCollection.Add` μέθοδος.

#### Ε: Μπορώ να προσαρμόσω περιεχόμενο κεφαλίδας ή υποσέλιδου με εικόνες και αριθμούς σελίδων στο Aspose.Words;

 Α: Ναι, μπορείτε να προσαρμόσετε περιεχόμενο κεφαλίδας ή υποσέλιδου με εικόνες και αριθμούς σελίδων στο Aspose.Words. Μπορείτε να χρησιμοποιήσετε αντικείμενα όπως`Shape` για να προσθέσετε εικόνες και αντικείμενα όπως`Field` για να προσθέσετε αριθμούς σελίδων στην κεφαλίδα ή το υποσέλιδο σας.

#### Ε: Μπορώ να αλλάξω τη γραμματοσειρά, το μέγεθος και το χρώμα του κειμένου στην κεφαλίδα ή το υποσέλιδο μου στο Aspose.Words;

 Α: Ναι, μπορείτε να αλλάξετε τη γραμματοσειρά, το μέγεθος και το χρώμα του κειμένου στην κεφαλίδα ή το υποσέλιδο σας στο Aspose.Words. Μπορείτε να αποκτήσετε πρόσβαση στις ιδιότητες μορφοποίησης κειμένου όπως π.χ`Font` για να αλλάξετε τη γραμματοσειρά,`Size` για να προσαρμόσετε το μέγεθος και`Color`για να ορίσετε το χρώμα του κειμένου.