---
title: Σελιδοδείκτης στηλών πίνακα στο έγγραφο του Word
linktitle: Σελιδοδείκτης στηλών πίνακα στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσθέτετε σελιδοδείκτη σε μια στήλη πίνακα σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-bookmarks/bookmark-table-columns/
---

Σε αυτό το άρθρο, θα εξερευνήσουμε τον πηγαίο κώδικα C# παραπάνω για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση σελιδοδεικτών πίνακα στηλών στη βιβλιοθήκη Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να προσθέσετε σελιδοδείκτη σε μια συγκεκριμένη στήλη ενός πίνακα σε ένα έγγραφο του Word και να αποκτήσετε πρόσβαση στο περιεχόμενο αυτής της στήλης.

## Προαπαιτούμενα

- Βασικές γνώσεις της γλώσσας C#.
- Περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

## Βήμα 1: Δημιουργία πίνακα

 Πριν δημιουργήσουμε έναν σελιδοδείκτη σε μια στήλη πίνακα, πρέπει πρώτα να δημιουργήσουμε τον πίνακα χρησιμοποιώντας το a`DocumentBuilder`αντικείμενο. Στο παράδειγμά μας, δημιουργούμε έναν πίνακα με δύο σειρές και δύο στήλες:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Βήμα 2: Δημιουργία του σελιδοδείκτη της στήλης

 Χρησιμοποιούμε το`StartBookmark` μέθοδο για τη δημιουργία ενός σελιδοδείκτη σε μια συγκεκριμένη στήλη του πίνακα. Στο παράδειγμά μας, χρησιμοποιούμε το όνομα "MyBookmark" για τον σελιδοδείκτη:

```csharp
builder. StartBookmark("MyBookmark");
```

## Βήμα 3: Πρόσβαση στο περιεχόμενο της στήλης

 Περνάμε όλους τους σελιδοδείκτες του εγγράφου και εμφανίζουμε τα ονόματά τους. Εάν ένας σελιδοδείκτης είναι στήλη, έχουμε πρόσβαση στα περιεχόμενα αυτής της στήλης χρησιμοποιώντας το ευρετήριο στήλης και το`GetText` μέθοδος:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Παράδειγμα πηγαίου κώδικα για στήλες πίνακα σελιδοδεικτών χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί το πλήρες δείγμα πηγαίου κώδικα για να καταδείξετε τη δημιουργία ενός σελιδοδείκτη σε μια στήλη πίνακα χρησιμοποιώντας το Aspose.Words για .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## συμπέρασμα

Σε αυτό το άρθρο, εξερευνήσαμε τον πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση σελιδοδεικτών πίνακα στηλών του Aspose.Words για .NET. Ακολουθήσαμε έναν οδηγό βήμα προς βήμα για να προσθέσετε σελιδοδείκτη σε μια συγκεκριμένη στήλη ενός πίνακα σε ένα έγγραφο του Word και να μεταβείτε στα περιεχόμενα αυτής της στήλης.

### Συχνές ερωτήσεις για στήλες πίνακα σελιδοδεικτών στο έγγραφο του Word

#### Ε: Ποιες είναι οι προϋποθέσεις για να χρησιμοποιήσετε τη δυνατότητα "Σελιδοδείκτες για στήλες πίνακα" στο Aspose.Words για .NET;

Α: Για να χρησιμοποιήσετε τη δυνατότητα "Σελιδοδείκτες για στήλες πίνακα" στο Aspose.Words για .NET, πρέπει να έχετε βασικές γνώσεις της γλώσσας C#. Χρειάζεστε επίσης ένα περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

#### Ε: Πώς να δημιουργήσετε έναν πίνακα με στήλες σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να δημιουργήσετε έναν πίνακα με στήλες σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε ένα`DocumentBuilder` αντικείμενο για εισαγωγή κελιών και περιεχομένου στον πίνακα. Εδώ είναι ένα δείγμα κώδικα:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### Ε: Πώς να προσθέσετε σελιδοδείκτη σε μια στήλη πίνακα χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να δημιουργήσετε έναν σελιδοδείκτη σε μια στήλη πίνακα χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`StartBookmark` μέθοδος του`DocumentBuilder` αντικείμενο να ξεκινήσει ο σελιδοδείκτης σε μια συγκεκριμένη στήλη πίνακα. Εδώ είναι ένα δείγμα κώδικα:

```csharp
builder.StartBookmark("MyBookmark");
```

#### Ε: Πώς να αποκτήσετε πρόσβαση σε περιεχόμενο στηλών πίνακα από σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET;

Α: Για να αποκτήσετε πρόσβαση στα περιεχόμενα μιας στήλης πίνακα από έναν σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να πραγματοποιήσετε αναζήτηση σε όλους τους σελιδοδείκτες του εγγράφου, να ελέγξετε εάν ένας σελιδοδείκτης είναι στήλη και να χρησιμοποιήσετε το ευρετήριο της στήλης για να αποκτήσετε πρόσβαση στα περιεχόμενα του εκείνη τη στήλη. Εδώ είναι ένα δείγμα κώδικα:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Κάντε κάτι με το περιεχόμενο της στήλης...
         }
     }
}
```

#### Ε: Υπάρχει όριο στον αριθμό των στηλών που μπορώ να δημιουργήσω σε έναν πίνακα με σελιδοδείκτες στηλών;

Α: Δεν υπάρχει συγκεκριμένο όριο στον αριθμό των στηλών που μπορείτε να δημιουργήσετε σε έναν πίνακα με σελιδοδείκτες στηλών χρησιμοποιώντας το Aspose.Words για .NET. Το όριο εξαρτάται κυρίως από τους διαθέσιμους πόρους στο σύστημά σας και τις προδιαγραφές της μορφής αρχείου Word που χρησιμοποιείτε. Ωστόσο, συνιστάται να μην δημιουργείτε υπερβολικά μεγάλο αριθμό στηλών, καθώς αυτό μπορεί να επηρεάσει την απόδοση και την αναγνωσιμότητα του τελικού εγγράφου.