---
title: Δημιουργία σελιδοδείκτη στο έγγραφο του Word
linktitle: Δημιουργία σελιδοδείκτη στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να δημιουργείτε σελιδοδείκτες στο έγγραφο του Word και να καθορίσετε τα επίπεδα προεπισκόπησης σελιδοδεικτών σε ένα PDF χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-bookmarks/create-bookmark/
---

Σε αυτό το άρθρο, θα εξερευνήσουμε τον πηγαίο κώδικα C# παραπάνω για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Δημιουργία σελιδοδείκτη στη βιβλιοθήκη Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να δημιουργείτε σελιδοδείκτες σε ένα έγγραφο και να προσδιορίζετε τα επίπεδα προεπισκόπησης σελιδοδεικτών σε ένα αρχείο PDF εξόδου.

## Προαπαιτούμενα

- Βασικές γνώσεις της γλώσσας C#.
- Περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

## Βήμα 1: Δημιουργία εγγράφου και γεννήτριας

 Πριν δημιουργήσουμε σελιδοδείκτες, πρέπει να δημιουργήσουμε ένα έγγραφο και ένα πρόγραμμα δημιουργίας εγγράφων χρησιμοποιώντας το`Document` και`DocumentBuilder` αντικείμενα:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 2: Δημιουργία του κύριου σελιδοδείκτη

 Χρησιμοποιούμε το`StartBookmark` μέθοδος έναρξης ενός κύριου σελιδοδείκτη και το`EndBookmark` τρόπος για να το τερματίσετε. Ενδιάμεσα, μπορούμε να προσθέσουμε κείμενο και άλλους σελιδοδείκτες:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Προσθέστε περισσότερους σελιδοδείκτες ή κείμενο εδώ.

builder. EndBookmark("My Bookmark");
```

## Βήμα 3: Δημιουργία ένθετων σελιδοδεικτών

 Μπορούμε επίσης να δημιουργήσουμε ένθετους σελιδοδείκτες μέσα σε έναν κύριο σελιδοδείκτη. Το ίδιο χρησιμοποιούμε`StartBookmark` και`EndBookmark` μέθοδοι δημιουργίας και τερματισμού ένθετων σελιδοδεικτών:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Βήμα 4: Καθορισμός επιπέδων προεπισκόπησης σελιδοδεικτών στο αρχείο PDF εξόδου

 Χρησιμοποιούμε το`PdfSaveOptions` αντικείμενο για να καθορίσετε τα επίπεδα προεπισκόπησης σελιδοδεικτών στο αρχείο PDF εξόδου. Χρησιμοποιούμε το`BookmarksOutlineLevels` ιδιοκτησία

  για να προσθέσετε κύριους σελιδοδείκτες και ένθετους σελιδοδείκτες με τα αντίστοιχα επίπεδά τους:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Παράδειγμα πηγαίου κώδικα για τη δημιουργία σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί το πλήρες παράδειγμα πηγαίου κώδικα για την επίδειξη της δημιουργίας σελιδοδεικτών χρησιμοποιώντας το Aspose.Words για .NET:

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## συμπέρασμα

Σε αυτό το άρθρο, εξερευνήσαμε τον πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Create Bookmark του Aspose.Words για .NET. Ακολουθήσαμε έναν οδηγό βήμα προς βήμα για τη δημιουργία σελιδοδεικτών σε ένα έγγραφο και τον καθορισμό των επιπέδων προεπισκόπησης σελιδοδεικτών σε ένα αρχείο PDF εξόδου.

### Συχνές ερωτήσεις

#### Ε: Ποιες είναι οι προϋποθέσεις για να χρησιμοποιήσετε τη λειτουργία "Δημιουργία σελιδοδεικτών" στο Aspose.Words για .NET;

Α: Για να χρησιμοποιήσετε τη λειτουργία "Δημιουργία σελιδοδεικτών" στο Aspose.Words για .NET, πρέπει να έχετε βασικές γνώσεις της γλώσσας C#. Χρειάζεστε επίσης ένα περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

#### Ε: Πώς να δημιουργήσετε ένα έγγραφο στο Aspose.Words για .NET;

 Α: Για να δημιουργήσετε ένα έγγραφο στο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Document` τάξη. Εδώ είναι ένα δείγμα κώδικα:

```csharp
Document doc = new Document();
```

#### Ε: Πώς να δημιουργήσετε έναν κύριο σελιδοδείκτη σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να δημιουργήσετε έναν κύριο σελιδοδείκτη σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`StartBookmark` μέθοδος για να ξεκινήσετε τον σελιδοδείκτη, να προσθέσετε κείμενο ή άλλους σελιδοδείκτες μέσα και, στη συνέχεια, χρησιμοποιήστε το` EndBookmark` να το τελειώσει. Εδώ είναι ένα δείγμα κώδικα:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Ε: Πώς να δημιουργήσετε έναν ένθετο σελιδοδείκτη μέσα σε έναν κύριο σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να δημιουργήσετε έναν ένθετο σελιδοδείκτη μέσα σε έναν κύριο σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το ίδιο`StartBookmark` και`EndBookmark` μεθόδους έναρξης και λήξης του ένθετου σελιδοδείκτη. Εδώ είναι ένα δείγμα κώδικα:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Ε: Πώς να καθορίσετε τα επίπεδα προεπισκόπησης σελιδοδεικτών σε ένα PDF εξόδου χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να καθορίσετε επίπεδα προεπισκόπησης σελιδοδεικτών σε ένα PDF εξόδου χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`PdfSaveOptions` τάξη και το`BookmarksOutlineLevels` ιδιοκτησία. Μπορείτε να προσθέσετε κύριους σελιδοδείκτες και ένθετους σελιδοδείκτες με τα αντίστοιχα επίπεδά τους. Εδώ είναι ένα δείγμα κώδικα:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Ε: Πώς να αποθηκεύσετε ένα έγγραφο μετά τη δημιουργία σελιδοδεικτών χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να αποθηκεύσετε ένα έγγραφο μετά τη δημιουργία σελιδοδεικτών χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Save` μέθοδος του`Document` αντικείμενο που καθορίζει τη διαδρομή του αρχείου προορισμού. Εδώ είναι ένα δείγμα κώδικα:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Ε: Πώς να καθορίσετε τα επίπεδα προεπισκόπησης σελιδοδεικτών σε ένα PDF εξόδου χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να καθορίσετε επίπεδα προεπισκόπησης σελιδοδεικτών σε ένα PDF εξόδου χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`PdfSaveOptions` τάξη και το`BookmarksOutlineLevels` ιδιοκτησία. Μπορείτε να προσθέσετε κύριους σελιδοδείκτες και ένθετους σελιδοδείκτες με τα αντίστοιχα επίπεδά τους. Εδώ είναι ένα δείγμα κώδικα:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Ε: Πώς να δημιουργήσετε ένθετους σελιδοδείκτες μέσα σε έναν κύριο σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να δημιουργήσετε ένθετους σελιδοδείκτες μέσα σε έναν κύριο σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το ίδιο`StartBookmark` και`EndBookmark` μεθόδους έναρξης και λήξης ένθετων σελιδοδεικτών. Βεβαιωθείτε ότι έχετε καθορίσει τον γονικό σελιδοδείκτη ως παράμετρο όταν καλείτε το`StartBookmark` μέθοδος. Εδώ είναι ένα δείγμα κώδικα:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### Ε: Πώς να προσθέσετε κείμενο μέσα σε έναν σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να προσθέσετε κείμενο μέσα σε έναν σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Write` μέθοδος του`DocumentBuilder`αντικείμενο που καθορίζει το κείμενο που θα προστεθεί. Εδώ είναι ένα δείγμα κώδικα:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Ε: Πώς να δημιουργήσετε έναν κύριο σελιδοδείκτη σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να δημιουργήσετε έναν κύριο σελιδοδείκτη σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`StartBookmark` μέθοδος έναρξης του σελιδοδείκτη και του`EndBookmark` τρόπος για να το τερματίσετε. Εδώ είναι ένα δείγμα κώδικα:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```