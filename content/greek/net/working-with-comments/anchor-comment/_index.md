---
title: Άγκυρα Σχόλιο
linktitle: Άγκυρα Σχόλιο
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να αγκυρώνετε τις απαντήσεις σχολίων σε συγκεκριμένο κείμενο σε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-comments/anchor-comment/
---

Σε αυτό το περιεκτικό σεμινάριο, θα μάθετε πώς να αγκυρώνετε τις απαντήσεις σχολίων σε συγκεκριμένο κείμενο σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας καθοδηγήσουμε στη διαδικασία και θα σας παρέχουμε τα απαραίτητα αποσπάσματα κώδικα C#. Μέχρι το τέλος αυτού του οδηγού, θα μπορείτε να συσχετίσετε σχόλια με συγκεκριμένο κείμενο στα έγγραφά σας.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Η βιβλιοθήκη Aspose.Words for .NET είναι εγκατεστημένη στο σύστημά σας.

## Βήμα 1: Δημιουργήστε ένα νέο έγγραφο και προσθέστε κείμενο
Για να ξεκινήσετε, δημιουργήστε ένα νέο έγγραφο χρησιμοποιώντας την κλάση Document και προσθέστε το επιθυμητό κείμενο:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Βήμα 2: Δημιουργήστε ένα σχόλιο και προσθέστε το εύρος σχολίων
Στη συνέχεια, δημιουργήστε ένα σχόλιο και συσχετίστε το με συγκεκριμένο κείμενο χρησιμοποιώντας αντικείμενα CommentRangeStart και CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Βήμα 3: Αποθηκεύστε το έγγραφο
Αφού αγκυρώσετε το σχόλιο σε συγκεκριμένο κείμενο, αποθηκεύστε το έγγραφο σε ένα αρχείο χρησιμοποιώντας τη μέθοδο Save της κλάσης Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Παράδειγμα πηγαίου κώδικα για απάντηση σχολίου Anchor χρησιμοποιώντας Aspose.Words για .NET
Ακολουθεί ο πλήρης πηγαίος κώδικας για την αγκύρωση μιας απάντησης σχολίου χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
// Δημιουργήστε μια παρουσία του Εγγράφου.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Δημιουργήστε τρία αντικείμενα Run.
// Τα δύο πρώτα εκτελούν κάποιο κείμενο, ενώ το τρίτο εκτελεί ένα σχόλιο

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Κάθε ένα από τα αντικείμενα Run έχει ένα συσχετισμένο αντικείμενο CommentRangeStart και CommentRangeEnd.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Συχνές ερωτήσεις

#### Ε: Τι είναι μια άγκυρα σχολίων στο Aspose.Words για .NET;

Α: Στο Aspose.Words για .NET, μια άγκυρα σχολίων είναι ένας δείκτης που συνδέει ένα σχόλιο με μια συγκεκριμένη θέση σε ένα έγγραφο.

#### Ε: Πώς μπορώ να προσθέσω μια άγκυρα σχολίων σε ένα έγγραφο Aspose.Words για .NET;

Α: Για να προσθέσετε μια άγκυρα σχολίων σε ένα έγγραφο Aspose.Words για .NET, ακολουθήστε τα βήματα που αναφέρονται στον οδηγό.

#### Ε: Πώς μπορώ να αποκτήσω πρόσβαση σε μια υπάρχουσα άγκυρα σχολίων στο Aspose.Words για .NET;

 Α: Μπορείτε να αποκτήσετε πρόσβαση σε μια υπάρχουσα άγκυρα σχολίων στο Aspose.Words για .NET χρησιμοποιώντας το`Comment.Anchor` ιδιοκτησία.

#### Ε: Μπορώ να προσθέσω μια άγκυρα σχολίων στο Aspose.Words για .NET;

 Α: Ναι, μπορείτε να αφαιρέσετε μια άγκυρα σχολίων στο Aspose.Words για .NET χρησιμοποιώντας το`Comment.Remove` μέθοδος.

#### Ε: Πώς μπορώ να επεξεργαστώ το κείμενο ενός σχολίου που συνδέεται με μια άγκυρα σχολίων στο Aspose.Words για .NET;

 Α: Για να τροποποιήσετε το κείμενο ενός σχολίου που είναι συνδεδεμένο σε μια άγκυρα σχολίων στο Aspose.Words για .NET, μπορείτε να αποκτήσετε πρόσβαση στο`Comment.Text` ιδιοκτησία του αντίστοιχου`Comment` αντικείμενο και τροποποιήστε το κείμενο όπως απαιτείται.

