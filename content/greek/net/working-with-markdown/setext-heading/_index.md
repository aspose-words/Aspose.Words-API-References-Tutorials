---
title: Επικεφαλίδα Setex
linktitle: Επικεφαλίδα Setex
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε τις επικεφαλίδες Setext για να μορφοποιήσετε τα έγγραφά σας με το Aspose.Words for .NET Βήμα προς βήμα οδηγό.
type: docs
weight: 10
url: /el/net/working-with-markdown/setext-heading/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα Setext Heading με το Aspose.Words για .NET. Το Setext Heading είναι μια εναλλακτική μέθοδος μορφοποίησης τίτλων σε έγγραφα Markdown.

## Βήμα 1: Χρήση ενός προγράμματος δημιουργίας εγγράφων

Αρχικά, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Βήμα 2: Χρήση του στυλ επικεφαλίδας Setext

Θα χρησιμοποιήσουμε το προεπιλεγμένο στυλ παραγράφου "Επικεφαλίδα 1" για να δημιουργήσουμε μια επικεφαλίδα επιπέδου 1 στο έγγραφό μας.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Βήμα 3: Επαναφορά στυλ

Επαναφέρουμε τα στυλ γραμματοσειράς που εφαρμόστηκαν προηγουμένως για να αποφύγουμε τυχόν ανεπιθύμητο συνδυασμό στυλ μεταξύ των παραγράφων.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Βήμα 4: Προσαρμογή των επιπέδων επικεφαλίδων Setext

Μπορούμε να προσαρμόσουμε τα επίπεδα επικεφαλίδων Setext προσθέτοντας νέα στυλ παραγράφου με βάση τα υπάρχοντα στυλ επικεφαλίδων. Σε αυτό το παράδειγμα, δημιουργούμε ένα στυλ "SetextHeading1" με βάση το στυλ "Heading 1" για να αντιπροσωπεύσουμε μια επικεφαλίδα επιπέδου 1 στη μορφή Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Βήμα 5: Αποθήκευση του εγγράφου

Τέλος, μπορούμε να αποθηκεύσουμε το έγγραφο στην επιθυμητή μορφή.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Παράδειγμα πηγαίου κώδικα για τίτλους Setext με Aspose.Words για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Χρησιμοποιήστε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσετε περιεχόμενο στο έγγραφο.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Επαναφέρετε τα στυλ από την προηγούμενη παράγραφο για να μην συνδυάζονται στυλ μεταξύ παραγράφων.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Επαναφέρετε τα στυλ από την προηγούμενη παράγραφο για να μην συνδυάζονται στυλ μεταξύ παραγράφων.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Το επίπεδο επικεφαλίδας Setex θα επαναφερθεί στο 2 εάν η βασική παράγραφος έχει επίπεδο επικεφαλίδας μεγαλύτερο από 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### Συχνές ερωτήσεις

#### Ε: Τι είναι η κεφαλίδα Setext Markdown;

Α: Η κεφαλίδα Setext Markdown είναι ένας εναλλακτικός τρόπος δημιουργίας επικεφαλίδων σε ένα έγγραφο Markdown. Χρησιμοποιεί χαρακτήρες υπογράμμισης (= ή -) για να υποδείξει διαφορετικά επίπεδα επικεφαλίδων.

#### Ε: Πώς να χρησιμοποιήσετε τις κεφαλίδες Setext Markdown;

Α: Για να χρησιμοποιήσετε επικεφαλίδες Setext Markdown, τοποθετήστε υπογράμμιση κάτω από το κείμενο του τίτλου. Χρησιμοποιήστε σύμβολα ίσου (=) για κεφαλίδα επιπέδου 1 και παύλες (-) για κεφαλίδα επιπέδου 2.

#### Ε: Υπάρχουν περιορισμοί στη χρήση των κεφαλίδων Setext Markdown;

Α: Οι επικεφαλίδες Setext Markdown έχουν περιορισμούς όσον αφορά την ιεραρχία επικεφαλίδων και δεν είναι τόσο διακριτές οπτικά όσο οι τυπικές επικεφαλίδες Markdown.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση των κεφαλίδων Setext Markdown;

Α: Στο τυπικό Markdown, δεν είναι δυνατή η προσαρμογή της εμφάνισης των κεφαλίδων Setext Markdown. Έχουν μια προκαθορισμένη εμφάνιση με βάση τους χαρακτήρες υπογράμμισης που χρησιμοποιούνται.

#### Ε: Υποστηρίζονται οι κεφαλίδες Setext Markdown από όλους τους επεξεργαστές Markdown;

Α: Η υποστήριξη για κεφαλίδες Setext Markdown ενδέχεται να διαφέρει μεταξύ των επεξεργαστών Markdown. Ελέγξτε τη συγκεκριμένη τεκμηρίωση του εκδότη σας για να βεβαιωθείτε.