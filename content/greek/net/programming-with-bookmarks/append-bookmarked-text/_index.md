---
title: Προσθήκη σελιδοδείκτη κειμένου σε έγγραφο του Word
linktitle: Προσθήκη σελιδοδείκτη κειμένου σε έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να προσθέτετε κείμενο από έναν σελιδοδείκτη σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-bookmarks/append-bookmarked-text/
---

Σε αυτό το άρθρο, θα εξερευνήσουμε τον παραπάνω πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Προσάρτησης σελιδοδείκτη κειμένου στη βιβλιοθήκη Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να προσθέσετε το κείμενο που περιέχεται σε έναν συγκεκριμένο σελιδοδείκτη ενός εγγράφου του Word σε άλλο έγγραφο.

## Προαπαιτούμενα

- Βασικές γνώσεις της γλώσσας C#.
- Περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

## Βήμα 1: Λήψη παραγράφων από το σελιδοδείκτη

 Πριν αρχίσουμε να προσθέτουμε το κείμενο του σελιδοδείκτη, πρέπει να λάβουμε τις παραγράφους που περιέχουν την αρχή και το τέλος του σελιδοδείκτη. Αυτό μπορεί να γίνει με πρόσβαση στο`BookmarkStart` και`BookmarkEnd` ιδιότητες του σελιδοδείκτη:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Βήμα 2: Ελέγξτε τις παραγράφους γονέα

Ελέγχουμε αν η αρχή και το τέλος της παραγράφου έχουν έγκυρους γονείς, αν δηλαδή ανήκουν όντως σε μια παράγραφο. Εάν όχι, δημιουργούμε μια εξαίρεση:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Βήμα 3: Ελέγξτε τους γονείς των παραγράφων

Ελέγχουμε αν η αρχή και η τελική παράγραφο έχουν τον ίδιο γονέα. Εάν όχι, αυτό σημαίνει ότι οι παράγραφοι δεν περιέχονται στην ίδια ενότητα ή έγγραφο και κάνουμε μια εξαίρεση:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Βήμα 4: Αντιγράψτε παραγράφους

Επαναλαμβάνουμε μέσα από τους κόμβους (παραγράφους) από την παράγραφο έναρξης έως την παράγραφο τέλους. Για κάθε κόμβο, δημιουργούμε ένα αντίγραφο και το εισάγουμε στο περιβάλλον του εγγράφου προορισμού:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Παράδειγμα πηγαίου κώδικα για Προσθήκη σελιδοδείκτη κειμένου χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί το πλήρες παράδειγμα πηγαίου κώδικα για την επίδειξη της προσθήκης κειμένου από έναν σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET:

```csharp

	// Αυτή είναι η παράγραφος που περιέχει την αρχή του σελιδοδείκτη.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Αυτή είναι η παράγραφος που περιέχει το τέλος του σελιδοδείκτη.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Περιοριζόμαστε σε ένα σχετικά απλό σενάριο.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Θέλουμε να αντιγράψουμε όλες τις παραγράφους από την παράγραφο αρχής μέχρι (και συμπεριλαμβανομένης) της παραγράφου τέλους,
	// επομένως ο κόμβος στον οποίο σταματάμε είναι ένας μετά την τελική παράγραφο.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Αυτό δημιουργεί ένα αντίγραφο του τρέχοντος κόμβου και το εισάγει (τον καθιστά έγκυρο) στο πλαίσιο
		// του εγγράφου προορισμού. Εισαγωγή σημαίνει σωστή προσαρμογή των στυλ και των αναγνωριστικών λιστών.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## συμπέρασμα

Σε αυτό το άρθρο, εξερευνήσαμε τον πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Append Bookmarked Text του Aspose.Words για .NET. Ακολουθήσαμε έναν οδηγό βήμα προς βήμα για τη λήψη παραγράφων από έναν σελιδοδείκτη, την επαλήθευση των γονέων και την αντιγραφή παραγράφων σε άλλο έγγραφο.

### Συχνές ερωτήσεις για την προσθήκη σελιδοδείκτη κειμένου στο έγγραφο του Word

#### Ε1: Ποιες είναι οι προϋποθέσεις για να χρησιμοποιήσετε τη δυνατότητα "Προσθήκη κειμένου με σελιδοδείκτες" στο Aspose.Words για .NET;

Α: Για να χρησιμοποιήσετε τη λειτουργία "Προσθήκη κειμένου με σελιδοδείκτες" στο Aspose.Words για .NET, πρέπει να έχετε βασικές γνώσεις της γλώσσας C#. Χρειάζεστε επίσης ένα περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

#### Ε2: Πώς να βρείτε τις παραγράφους που περιέχουν την αρχή και το τέλος ενός σελιδοδείκτη σε ένα έγγραφο του Word;

Α: Για να λάβετε τις παραγράφους που περιέχουν την αρχή και το τέλος ενός σελιδοδείκτη σε ένα έγγραφο του Word, μπορείτε να αποκτήσετε πρόσβαση στο`BookmarkStart` και`BookmarkEnd` ιδιότητες του σελιδοδείκτη. Εδώ είναι ένα δείγμα κώδικα:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Ε3: Τι συμβαίνει εάν οι παράγραφοι έναρξης και λήξης δεν έχουν έγκυρους γονείς;

Α: Εάν οι παράγραφοι έναρξης και λήξης δεν έχουν έγκυρους γονείς, δηλαδή δεν είναι στην πραγματικότητα παράγραφοι, θα γίνει εξαίρεση. Αυτή η κατάσταση δεν μπορεί να διαχειριστεί αυτήν τη στιγμή.
