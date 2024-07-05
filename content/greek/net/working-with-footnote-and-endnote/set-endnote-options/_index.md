---
title: Ορίστε τις επιλογές σημείωσης τέλους
linktitle: Ορίστε τις επιλογές σημείωσης τέλους
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ορίζετε επιλογές σημειώσεων τέλους σε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET. Οδηγός βήμα προς βήμα με παράδειγμα πηγαίο κώδικα.
type: docs
weight: 10
url: /el/net/working-with-footnote-and-endnote/set-endnote-options/
---

Σε αυτό το βήμα προς βήμα σεμινάριο, θα σας καθοδηγήσουμε σχετικά με τον τρόπο χρήσης του Aspose.Words για .NET για να ορίσετε επιλογές σημειώσεων τέλους σε ένα έγγραφο του Word. Θα εξηγήσουμε τον παρεχόμενο πηγαίο κώδικα C# και θα σας δείξουμε πώς να τον εφαρμόσετε στα δικά σας έργα.

 Για να ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει το Aspose.Words για .NET στο περιβάλλον ανάπτυξης σας. Εάν δεν το έχετε κάνει, κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από[Aspose.Releases]https://releases.aspose.com/words/net/.

## Βήμα 1: Αρχικοποίηση του αντικειμένου εγγράφου

 Αρχικά, αρχικοποιήστε το`Document` αντικείμενο παρέχοντας τη διαδρομή προς το έγγραφο προέλευσης:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Βήμα 2: Αρχικοποίηση του αντικειμένου του DocumentBuilder

 Στη συνέχεια, αρχικοποιήστε το`DocumentBuilder` αντικείμενο να εκτελέσει λειτουργίες στο έγγραφο:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Προσθήκη κειμένου και σημείωσης τέλους

 Χρησιμοποιήστε το`Write` μέθοδος του`DocumentBuilder` αντικείμενο για προσθήκη κειμένου στο έγγραφο και το`InsertFootnote` μέθοδος εισαγωγής σημείωσης τέλους:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Βήμα 4: Ρύθμιση επιλογών σημείωσης τέλους

 Πρόσβαση στο`EndnoteOptions`ιδιότητα του εγγράφου για την τροποποίηση των επιλογών σημειώσεων τέλους. Σε αυτό το παράδειγμα, ορίσαμε τον κανόνα επανεκκίνησης για επανεκκίνηση σε κάθε σελίδα και τη θέση στο τέλος της ενότητας:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Βήμα 5: Αποθήκευση του εγγράφου

Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Αυτό είναι! Έχετε ορίσει με επιτυχία τις επιλογές σημείωσης τέλους σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για το Set Endnote Options χρησιμοποιώντας το Aspose.Words για .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Μη διστάσετε να χρησιμοποιήσετε αυτόν τον κωδικό στα δικά σας έργα και να τον τροποποιήσετε σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να διαμορφώσω τις σημειώσεις τέλους στο Aspose.Words;

 Α: Για να διαμορφώσετε τις σημειώσεις τέλους στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`EndnoteOptions` τάξη και το`SeparatorNoteTextStyle` ιδιοκτησία. Μπορείτε να καθορίσετε στυλ γραμματοσειράς, μέγεθος, χρώμα κ.λπ. για σημειώσεις τέλους χρησιμοποιώντας αυτήν την ιδιότητα.

#### Ε: Είναι δυνατή η προσαρμογή της αρίθμησης των σημειώσεων τέλους σε ένα έγγραφο;

 Α: Ναι, είναι δυνατή η προσαρμογή της αρίθμησης των σημειώσεων τέλους σε ένα έγγραφο. Μπορείτε να χρησιμοποιήσετε το`RestartRule` και`NumberStyle` ιδιότητες του`EndnoteOptions` κλάση για τον καθορισμό συγκεκριμένων κανόνων επανεκκίνησης και στυλ αρίθμησης.

#### Ε: Πώς μπορώ να τοποθετήσω τις σημειώσεις τέλους σε ένα έγγραφο;

Α: Για να τοποθετήσετε τις σημειώσεις τέλους σε ένα έγγραφο, μπορείτε να χρησιμοποιήσετε το`Position` ιδιοκτησία του`EndnoteOptions` τάξη. Μπορείτε να καθορίσετε εάν οι σημειώσεις τέλους θα πρέπει να τοποθετούνται στο κάτω μέρος κάθε σελίδας, στο τέλος κάθε ενότητας ή στο τέλος του εγγράφου.

#### Ε: Μπορώ να προσαρμόσω τη μορφή αρίθμησης σημειώσεων τέλους;

 Α: Ναι, μπορείτε να προσαρμόσετε τη μορφή αρίθμησης σημειώσεων τέλους στο Aspose.Words. Χρησιμοποιήστε το`NumberFormat` ιδιοκτησία του`EndnoteOptions` τάξη για να ορίσετε την επιθυμητή μορφή, όπως αραβικούς αριθμούς, λατινικούς αριθμούς, γράμματα κ.λπ.

#### Ε: Είναι δυνατόν να συνεχιστεί η αρίθμηση σημειώσεων τέλους μεταξύ των ενοτήτων ενός εγγράφου;

 Α: Ναι, είναι δυνατό να συνεχιστεί η αρίθμηση σημειώσεων τέλους μεταξύ των ενοτήτων ενός εγγράφου. Χρησιμοποιήστε το`RestartRule` ιδιοκτησία του`EndnoteOptions` τάξη και ρυθμίστε το σε`RestartContinuous` για να επιτραπεί η συνέχιση της αρίθμησης μεταξύ των ενοτήτων.