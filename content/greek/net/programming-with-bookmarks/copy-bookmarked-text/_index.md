---
title: Αντιγράψτε το σελιδοδείκτη κειμένου σε έγγραφο του Word
linktitle: Αντιγράψτε το σελιδοδείκτη κειμένου σε έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να αντιγράφετε κείμενο σελιδοδείκτη στο έγγραφο word σε άλλο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-bookmarks/copy-bookmarked-text/
---

Σε αυτό το άρθρο, θα εξερευνήσουμε τον πηγαίο κώδικα C# παραπάνω για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Copy Bookmarked Text στη βιβλιοθήκη Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να αντιγράψετε τα περιεχόμενα ενός συγκεκριμένου σελιδοδείκτη από ένα έγγραφο προέλευσης σε άλλο έγγραφο.

## Προαπαιτούμενα

- Βασικές γνώσεις της γλώσσας C#.
- Περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

## Βήμα 1: Φόρτωση εγγράφου προέλευσης

 Πριν αντιγράψουμε το κείμενο του σελιδοδείκτη, πρέπει να φορτώσουμε το έγγραφο προέλευσης στο α`Document` αντικείμενο χρησιμοποιώντας τη διαδρομή αρχείου:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Βήμα 2: Λήψη σελιδοδείκτη πηγής

 Χρησιμοποιούμε το`Bookmarks` ιδιότητα του εύρους του εγγράφου προέλευσης για να λάβουμε τον συγκεκριμένο σελιδοδείκτη που θέλουμε να αντιγράψουμε:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Βήμα 3: Δημιουργία του εγγράφου προορισμού

Δημιουργούμε ένα νέο έγγραφο που θα χρησιμεύσει ως έγγραφο προορισμού για την αντιγραφή του περιεχομένου του σελιδοδείκτη:

```csharp
Document dstDoc = new Document();
```

## Βήμα 4: Καθορισμός της θέσης αντιγραφής

Καθορίζουμε τη θέση όπου θέλουμε να προσθέσουμε το αντιγραμμένο κείμενο. Στο παράδειγμά μας, προσθέτουμε το κείμενο στο τέλος του σώματος της τελευταίας ενότητας του εγγράφου προορισμού:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Βήμα 5: Εισαγωγή και αντιγραφή κειμένου σελιδοδεικτών

 Χρησιμοποιούμε α`NodeImporter`αντικείμενο εισαγωγής και αντιγραφή κειμένου σελιδοδείκτη από ένα έγγραφο προέλευσης στο έγγραφο προορισμού:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Παράδειγμα πηγαίου κώδικα για Αντιγραφή σελιδοδείκτη κειμένου χρησιμοποιώντας το Aspose.Words για .NET

Ακολουθεί το πλήρες παράδειγμα πηγαίου κώδικα για την επίδειξη της αντιγραφής κειμένου από έναν σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET:

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Αυτός είναι ο σελιδοδείκτης του οποίου το περιεχόμενο θέλουμε να αντιγράψουμε.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Θα προσθέσουμε σε αυτό το έγγραφο.
	Document dstDoc = new Document();

	// Ας πούμε ότι θα προσαρτηθούμε στο τέλος του σώματος του τελευταίου τμήματος.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Εάν κάνετε εισαγωγή πολλές φορές χωρίς ένα μόνο περιβάλλον, θα έχει ως αποτέλεσμα τη δημιουργία πολλών στυλ.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AppendBookmarkedText Πηγαίος κώδικας

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
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
        }

```
## συμπέρασμα

Σε αυτό το άρθρο, εξερευνήσαμε τον πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Αντιγραφή σελιδοδείκτη κειμένου από το Aspose.Words για .NET. Ακολουθήσαμε έναν οδηγό βήμα προς βήμα για να αντιγράψουμε τα περιεχόμενα ενός σελιδοδείκτη από ένα έγγραφο προέλευσης σε άλλο έγγραφο.

### Συχνές ερωτήσεις για την αντιγραφή κειμένου με σελιδοδείκτη σε έγγραφο του Word

#### Ε: Ποιες είναι οι απαιτήσεις για τη χρήση της δυνατότητας "Αντιγραφή κειμένου με σελιδοδείκτες" στο Aspose.Words για .NET;

Α: Για να χρησιμοποιήσετε τη δυνατότητα "Αντιγραφή κειμένου με σελιδοδείκτες" στο Aspose.Words για .NET, πρέπει να έχετε βασικές γνώσεις της γλώσσας C#. Χρειάζεστε επίσης ένα περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

#### Ε: Πώς μπορώ να φορτώσω ένα έγγραφο προέλευσης στο Aspose.Words για .NET;

 Α: Για να φορτώσετε ένα έγγραφο προέλευσης στο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Document` κλάση καθορίζοντας τη διαδρομή αρχείου του εγγράφου. Εδώ είναι ένα δείγμα κώδικα:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Ε: Πώς να αποκτήσετε το περιεχόμενο ενός συγκεκριμένου σελιδοδείκτη σε ένα έγγραφο προέλευσης χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να λάβετε τα περιεχόμενα ενός συγκεκριμένου σελιδοδείκτη σε ένα έγγραφο προέλευσης χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να αποκτήσετε πρόσβαση στο`Bookmarks` ιδιότητα του εύρους εγγράφου προέλευσης και χρησιμοποιήστε το όνομα του σελιδοδείκτη για να ανακτήσετε τον συγκεκριμένο σελιδοδείκτη . Εδώ είναι ένα δείγμα κώδικα:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Ε: Πώς να καθορίσετε τη θέση του αντιγράφου κειμένου σελιδοδείκτη σε ένα έγγραφο προορισμού χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να καθορίσετε πού θέλετε να προσθέσετε αντιγραμμένο κείμενο σελιδοδείκτη σε ένα έγγραφο προορισμού χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να πλοηγηθείτε στο σώμα της τελευταίας ενότητας του εγγράφου προορισμού. Μπορείτε να χρησιμοποιήσετε το`LastSection` ιδιοκτησία για πρόσβαση στο τελευταίο τμήμα και το`Body` ιδιοκτησία για πρόσβαση στο σώμα αυτού του τμήματος. Εδώ είναι ένα δείγμα κώδικα:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Ε: Πώς να εισαγάγετε και να αντιγράψετε κείμενο σελιδοδεικτών από το έγγραφο προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να εισαγάγετε και να αντιγράψετε κείμενο σελιδοδείκτη από ένα έγγραφο προέλευσης σε ένα έγγραφο προορισμού χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`NodeImporter` κλάση που καθορίζει το έγγραφο προέλευσης, το έγγραφο προορισμού και τη λειτουργία μορφοποίησης προς διατήρηση. Στη συνέχεια, μπορείτε να χρησιμοποιήσετε το`AppendBookmarkedText` μέθοδος για την προσθήκη του κειμένου σελιδοδείκτη στο έγγραφο προορισμού. Εδώ είναι ένα δείγμα κώδικα:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Ε: Πώς να αποθηκεύσετε ένα έγγραφο προορισμού μετά την αντιγραφή κειμένου σελιδοδεικτών χρησιμοποιώντας το Aspose.Words για .NET;

Α: Για να αποθηκεύσετε ένα έγγραφο προορισμού μετά την αντιγραφή κειμένου από έναν σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Save` μέθοδος του`Document` αντικείμενο που καθορίζει τη διαδρομή του αρχείου προορισμού. Εδώ είναι ένα δείγμα κώδικα:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```