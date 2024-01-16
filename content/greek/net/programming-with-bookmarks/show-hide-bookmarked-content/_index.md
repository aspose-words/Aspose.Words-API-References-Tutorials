---
title: Εμφάνιση Απόκρυψης σελιδοδείκτη περιεχομένου στο έγγραφο του Word
linktitle: Εμφάνιση Απόκρυψης σελιδοδείκτη περιεχομένου στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εμφανίζετε ή να αποκρύπτετε περιεχόμενο σελιδοδεικτών στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Σε αυτό το άρθρο, θα εξερευνήσουμε τον παραπάνω πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη λειτουργία Εμφάνιση απόκρυψης σελιδοδείκτη περιεχομένου στη βιβλιοθήκη Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να εμφανίζετε ή να αποκρύπτετε τα περιεχόμενα ενός σελιδοδείκτη στο έγγραφο του Word βάσει μιας συγκεκριμένης συνθήκης κατά τη συγχώνευση δεδομένων.

## Προαπαιτούμενα

- Βασικές γνώσεις της γλώσσας C#.
- Περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

## Βήμα 1: Λήψη του σελιδοδείκτη

 Χρησιμοποιούμε το`Bookmarks` ιδιότητα του εύρους εγγράφων για να λάβουμε τον συγκεκριμένο σελιδοδείκτη στον οποίο θέλουμε να εμφανίσουμε ή να αποκρύψουμε το περιεχόμενο:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Βήμα 2: Εισαγωγή των πεδίων συγχώνευσης

 Χρησιμοποιούμε πρόγραμμα δημιουργίας εγγράφων`DocumentBuilder` για να εισαγάγετε τα απαραίτητα πεδία συγχώνευσης. Αυτά τα πεδία συγχώνευσης θα ορίσουν μια συνθήκη για εμφάνιση ή απόκρυψη του περιεχομένου σελιδοδεικτών ανάλογα με την τιμή του`showHide` μεταβλητός:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Βήμα 3: Μετακίνηση περιεχομένου σελιδοδεικτών

Πραγματοποιούμε κύκλο στα περιεχόμενα του σελιδοδείκτη και τον μετακινούμε έτσι ώστε να εμφανίζεται

isse πριν από τον σελιδοδείκτη. Αυτό θα ελέγξει την εμφάνιση ή την απόκρυψη περιεχομένου με βάση την καθορισμένη συνθήκη:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Βήμα 4: Μετακίνηση του υπόλοιπου περιεχομένου σελιδοδεικτών

Μετακινούμε το υπόλοιπο περιεχόμενο του σελιδοδείκτη μετά τον σελιδοδείκτη, χρησιμοποιώντας τον τελικό κόμβο του σελιδοδείκτη ως σημείο εισαγωγής:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Βήμα 5: Εκτέλεση της συγχώνευσης

 Χρησιμοποιούμε το`Execute` μέθοδο του εγγράφου`s `Συγχώνευση αλληλογραφίας` object to execute the merge using the bookmark name and the value of the `μεταβλητή showHide`:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Παράδειγμα πηγαίου κώδικα για Εμφάνιση απόκρυψης σελιδοδείκτη περιεχομένου με χρήση του Aspose.Words για .NET

Ακολουθεί το πλήρες παράδειγμα πηγαίου κώδικα για την επίδειξη εμφάνισης ή απόκρυψης περιεχομένου σελιδοδεικτών χρησιμοποιώντας το Aspose.Words για .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD bookmark}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## συμπέρασμα

Σε αυτό το άρθρο, εξερευνήσαμε τον πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα Εμφάνιση απόκρυψης σελιδοδείκτη περιεχομένου του Aspose.Words για .NET. Ακολουθήσαμε έναν οδηγό βήμα προς βήμα για να εμφανίσουμε ή να αποκρύψουμε τα περιεχόμενα ενός σελιδοδείκτη με βάση μια συγκεκριμένη συνθήκη κατά τη συγχώνευση δεδομένων.

### Συχνές ερωτήσεις για εμφάνιση απόκρυψη περιεχομένου σελιδοδείκτη στο έγγραφο του Word

#### Ε: Μπορώ να χρησιμοποιήσω την ίδια συνθήκη για πολλούς σελιδοδείκτες στο ίδιο έγγραφο;

Α: Ναι, μπορείτε να χρησιμοποιήσετε την ίδια συνθήκη για πολλούς σελιδοδείκτες στο ίδιο έγγραφο. Απλώς επαναλάβετε τα βήματα 2-5 για κάθε σελιδοδείκτη, προσαρμόζοντας το όνομα του σελιδοδείκτη και προαιρετικά την τιμή του`showhide` μεταβλητή ανάλογα με τις ανάγκες.

#### Ε: Πώς μπορώ να προσθέσω περισσότερες συνθήκες για εμφάνιση ή απόκρυψη περιεχομένου σελιδοδεικτών;

 Α: Για να προσθέσετε περισσότερες συνθήκες, μπορείτε να χρησιμοποιήσετε λογικούς τελεστές όπως π.χ`AND` και`OR` στον κώδικα για την εισαγωγή των πεδίων συγχώνευσης στο βήμα 2. Επεξεργαστείτε τη συνθήκη στον ακόλουθο κώδικα για να προσθέσετε πρόσθετες συνθήκες:

```csharp
builder. Write("\" = \"true\" ");
```

#### Ε: Πώς μπορώ να διαγράψω έναν σελιδοδείκτη σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να αφαιρέσετε έναν σελιδοδείκτη σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Remove` μέθοδος από το`Bookmarks` συλλογή του εύρους εγγράφων. Ακολουθεί δείγμα κώδικα για τη διαγραφή ενός συγκεκριμένου σελιδοδείκτη:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Ε: Είναι η βιβλιοθήκη Aspose.Words δωρεάν;

 Α: Η βιβλιοθήκη Aspose.Words είναι μια εμπορική βιβλιοθήκη και απαιτεί έγκυρη άδεια χρήσης για χρήση στα έργα σας. Μπορείς να ελέγξεις[Aspose.Words για αναφορές API .NET](https://reference.aspose.com/words/net/) για να μάθετε περισσότερα σχετικά με τις επιλογές αδειοδότησης και τις τιμές.

#### Ε: Υπάρχουν άλλες διαθέσιμες βιβλιοθήκες για επεξεργασία κειμένου με έγγραφα Word στο .NET;

Α: Ναι, υπάρχουν άλλες βιβλιοθήκες διαθέσιμες για επεξεργασία κειμένου με έγγραφα Word στο .NET, όπως το Open XML SDK και το GemBox.Document. Μπορείτε να εξερευνήσετε αυτές τις βιβλιοθήκες ως εναλλακτικές στο Aspose.Words με βάση τις συγκεκριμένες ανάγκες και προτιμήσεις σας.