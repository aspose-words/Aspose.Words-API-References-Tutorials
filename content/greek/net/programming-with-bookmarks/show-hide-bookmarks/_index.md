---
title: Εμφάνιση απόκρυψης σελιδοδεικτών στο έγγραφο του Word
linktitle: Εμφάνιση απόκρυψης σελιδοδεικτών στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εμφανίζετε ή να αποκρύπτετε έναν συγκεκριμένο σελιδοδείκτη στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-bookmarks/show-hide-bookmarks/
---

Σε αυτό το άρθρο, θα εξερευνήσουμε τον πηγαίο κώδικα C# παραπάνω για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Εμφάνιση απόκρυψης σελιδοδεικτών στη βιβλιοθήκη Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να εμφανίζετε ή να αποκρύπτετε έναν συγκεκριμένο σελιδοδείκτη στο έγγραφο του Word.

## Προαπαιτούμενα

- Βασικές γνώσεις της γλώσσας C#.
- Περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

## Βήμα 1: Φόρτωση του εγγράφου

 Χρησιμοποιούμε το`Document` κλάση για να φορτώσει το υπάρχον έγγραφο από ένα αρχείο:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Βήμα 2: Εμφάνιση ή απόκρυψη ενός συγκεκριμένου σελιδοδείκτη

 Χρησιμοποιούμε το`ShowHideBookmarkedContent`λειτουργία για εμφάνιση ή απόκρυψη ενός συγκεκριμένου σελιδοδείκτη στο έγγραφο. Αυτή η συνάρτηση λαμβάνει ως παραμέτρους το έγγραφο, το όνομα του σελιδοδείκτη και ένα boolean για να δείξει εάν θα εμφανιστεί ή θα αποκρύψει ο σελιδοδείκτης:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Βήμα 3: Αποθήκευση του τροποποιημένου εγγράφου

 Χρησιμοποιούμε το`Save` μέθοδος αποθήκευσης του τροποποιημένου εγγράφου σε αρχείο:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Παράδειγμα πηγαίου κώδικα για Εμφάνιση Απόκρυψης Σελιδοδεικτών με χρήση του Aspose.Words για .NET

Ακολουθεί το πλήρες παράδειγμα πηγαίου κώδικα για να δείξετε την εμφάνιση ή την απόκρυψη ενός συγκεκριμένου σελιδοδείκτη χρησιμοποιώντας το Aspose.Words για .NET:

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent πηγαίος κώδικας

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
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
        }
		
```
## συμπέρασμα

Σε αυτό το άρθρο, εξερευνήσαμε τον πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα Εμφάνιση απόκρυψης σελιδοδεικτών του Aspose.Words για .NET. Ακολουθήσαμε έναν οδηγό βήμα προς βήμα για να εμφανίσουμε ή να αποκρύψουμε έναν συγκεκριμένο σελιδοδείκτη σε ένα έγγραφο.

### Συχνές ερωτήσεις για εμφάνιση απόκρυψης σελιδοδεικτών στο έγγραφο του Word

#### Ε: Μπορώ να εμφανίσω ή να αποκρύψω πολλούς σελιδοδείκτες στο ίδιο έγγραφο;

Α: Ναι, μπορείτε να εμφανίσετε ή να αποκρύψετε πολλούς σελιδοδείκτες στο ίδιο έγγραφο επαναλαμβάνοντας τα βήματα 2 και 3 για κάθε σελιδοδείκτη που θέλετε να επεξεργαστείτε.

#### Ε: Ο παρεχόμενος κώδικας λειτουργεί με άλλες μορφές εγγράφων του Word, όπως .doc ή .docm;

Α: Ναι, ο παρεχόμενος κώδικας λειτουργεί με διάφορες μορφές εγγράφων του Word που υποστηρίζονται από το Aspose.Words, όπως .doc και .docm. Απλώς βεβαιωθείτε ότι χρησιμοποιείτε το σωστό όνομα αρχείου και διαδρομή κατά τη φόρτωση και την αποθήκευση του εγγράφου.

#### Ε: Πώς μπορώ να εμφανίσω ξανά έναν κρυφό σελιδοδείκτη;

 Α: Για να εμφανίσετε ξανά έναν κρυφό σελιδοδείκτη, πρέπει να χρησιμοποιήσετε τον ίδιο`ShowHideBookmarkedContent` συνάρτηση περνώντας την τιμή`true` για τη δυαδική παράμετρο που υποδεικνύει εάν θα εμφανιστεί ή θα αποκρύψετε τον σελιδοδείκτη.

#### Ε: Μπορώ να χρησιμοποιήσω συνθήκες για την εμφάνιση ή την απόκρυψη σελιδοδεικτών με βάση τις τιμές των πεδίων συγχώνευσης στο έγγραφο;

 Α: Ναι, μπορείτε να χρησιμοποιήσετε συνθήκες και να συγχωνεύσετε τιμές πεδίων για να προσδιορίσετε εάν ένας σελιδοδείκτης πρέπει να εμφανίζεται ή να κρυφτεί. Μπορείτε να προσαρμόσετε τον κωδικό του`ShowHideBookmarkedContent` λειτουργία για να λαμβάνει υπόψη τις κατάλληλες συνθήκες και τιμές.

#### Ε: Πώς μπορώ να διαγράψω έναν σελιδοδείκτη σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να αφαιρέσετε έναν σελιδοδείκτη σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`RemoveBookmarks` μέθοδος του`Document` τάξη. Εδώ είναι ένα δείγμα κώδικα:

```csharp
doc.RemoveBookmarks("BookmarkName");
```