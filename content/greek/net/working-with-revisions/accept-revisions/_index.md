---
title: Αποδοχή αναθεωρήσεων
linktitle: Αποδοχή αναθεωρήσεων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να αποδέχεστε αναθεωρήσεις σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET
type: docs
weight: 10
url: /el/net/working-with-revisions/accept-revisions/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στην αποδοχή αναθεωρήσεων σε ένα έγγραφο του Word χρησιμοποιώντας τη δυνατότητα Αποδοχή αναθεωρήσεων του Aspose.Words για .NET. Ακολουθήστε τα παρακάτω βήματα για να κατανοήσετε τον πηγαίο κώδικα και να αποδεχτείτε τις αλλαγές στο έγγραφο.

## Βήμα 1: Προσθήκη και επεξεργασία περιεχομένου εγγράφου

Σε αυτό το παράδειγμα, δημιουργούμε ένα έγγραφο και προσθέτουμε περιεχόμενο. Χρησιμοποιούμε πολλές παραγράφους για να απεικονίσουμε αλλαγές και αναθεωρήσεις. Δείτε πώς:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Προσθέστε κείμενο στην πρώτη παράγραφο και, στη συνέχεια, προσθέστε δύο ακόμη παραγράφους.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Βήμα 2: Παρακολουθήστε κριτικές και προσθέστε κριτικές

Ενεργοποιούμε την παρακολούθηση αναθεωρήσεων και προσθέτουμε μια αναθεώρηση στο έγγραφο. Δείτε πώς:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Αυτή η παράγραφος είναι μια αναθεώρηση και θα έχει οριστεί η αντίστοιχη σημαία "IsInsertRevision".
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Βήμα 3: Διαγράψτε μια παράγραφο και διαχειριστείτε τις αναθεωρήσεις

Διαγράφουμε μια παράγραφο και ελέγχουμε για αποθηκευμένες αναθεωρήσεις. Δείτε πώς:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Καθώς παρακολουθούμε τις αναθεωρήσεις, η παράγραφος εξακολουθεί να υπάρχει στο έγγραφο, θα έχει οριστεί η σημαία "IsDeleteRevision"
// και θα εμφανίζεται ως κριτική στο Microsoft Word, έως ότου αποδεχθούμε ή απορρίψουμε όλες τις αξιολογήσεις.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Βήμα 4: Αποδοχή αλλαγών

Αποδεχόμαστε όλες τις αλλαγές στο έγγραφο. Δείτε πώς:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Βήμα 5: Διακοπή παρακολούθησης κριτικών

Θα σταματήσουμε να παρακολουθούμε τις αναθεωρήσεις, έτσι ώστε οι αλλαγές στο έγγραφο να μην εμφανίζονται πλέον ως αναθεωρήσεις. Δείτε πώς:

```csharp
doc.StopTrackRevisions();
```
## Βήμα 6: Αποθήκευση του εγγράφου

 Αφού εισαγάγετε το πεδίο φόρμας εισαγωγής κειμένου, αποθηκεύστε το έγγραφο στην επιθυμητή θέση χρησιμοποιώντας το`Save` μέθοδος. Φροντίστε να παρέχετε την κατάλληλη διαδρομή αρχείου:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Παράδειγμα πηγαίου κώδικα για Αποδοχή αναθεωρήσεων χρησιμοποιώντας Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για την αποδοχή αλλαγών σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET:


```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Προσθέστε κείμενο στην πρώτη παράγραφο και, στη συνέχεια, προσθέστε δύο ακόμη παραγράφους.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Έχουμε τρεις παραγράφους, καμία από τις οποίες δεν έχει καταχωρηθεί ως οποιοδήποτε είδος αναθεώρησης
// Εάν προσθέσουμε/αφαιρέσουμε οποιοδήποτε περιεχόμενο στο έγγραφο κατά την παρακολούθηση των αναθεωρήσεων,
// θα εμφανίζονται ως τέτοια στο έγγραφο και μπορούν να γίνουν αποδεκτά/απορριφθέντα.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Αυτή η παράγραφος είναι μια αναθεώρηση και θα έχει το αντίστοιχο σύνολο σημαιών "IsInsertRevision".
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Αποκτήστε τη συλλογή παραγράφων του εγγράφου και αφαιρέστε μια παράγραφο.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Εφόσον παρακολουθούμε τις αναθεωρήσεις, η παράγραφος εξακολουθεί να υπάρχει στο έγγραφο, θα έχει οριστεί το "IsDeleteRevision"
// και θα εμφανίζεται ως αναθεώρηση στο Microsoft Word, μέχρι να αποδεχθούμε ή να απορρίψουμε όλες τις αναθεωρήσεις.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Η παράγραφος διαγραφής αναθεώρησης καταργείται μόλις αποδεχθούμε τις αλλαγές.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Η διακοπή της παρακολούθησης των αναθεωρήσεων κάνει αυτό το κείμενο να εμφανίζεται ως κανονικό κείμενο.
// Οι αναθεωρήσεις δεν υπολογίζονται όταν αλλάζει το έγγραφο.
doc.StopTrackRevisions();

// Αποθηκεύστε το έγγραφο.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να αποδεχόμαστε αναθεωρήσεις σε ένα έγγραφο του Word χρησιμοποιώντας τη δυνατότητα Αποδοχή αναθεωρήσεων του Aspose.Words για .NET. Ακολουθήσαμε τα βήματα για να προσθέσουμε και να επεξεργαστούμε περιεχόμενο εγγράφου, να παρακολουθήσουμε αναθεωρήσεις, να διαγράψουμε μια αναθεωρημένη παράγραφο, να αποδεχθούμε όλες τις αλλαγές και να σταματήσουμε την παρακολούθηση αναθεωρήσεων. Τώρα μπορείτε να εφαρμόσετε αυτές τις γνώσεις για να διαχειριστείτε αποτελεσματικά τις αναθεωρήσεις στα δικά σας έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να ενεργοποιήσω την παρακολούθηση αναθεωρήσεων στο Aspose.Words για .NET;

#### Λύση 1:

 Α: Για να ενεργοποιήσετε την παρακολούθηση αναθεωρήσεων στο Aspose.Words για .NET, χρησιμοποιήστε το`StartTrackRevisions` μέθοδος του`Document` αντικείμενο και καθορίστε το όνομα του συγγραφέα και την ημερομηνία έναρξης για την παρακολούθηση αναθεωρήσεων.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Λύση 2:

 Α: Μπορείτε επίσης να ενεργοποιήσετε την παρακολούθηση αναθεωρήσεων χρησιμοποιώντας το`Document` κατασκευαστής που δέχεται`trackRevisions` και`author` Παράμετροι.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Ε: Πώς να αποδεχτείτε όλες τις αλλαγές σε ένα έγγραφο με το Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`AcceptAllRevisions` μέθοδος του`Document` αντίρρηση να αποδεχτεί όλες τις αλλαγές που έγιναν στο έγγραφο.

```csharp
doc.AcceptAllRevisions();
```

#### Ε: Πώς μπορώ να αποθηκεύσω ένα τροποποιημένο έγγραφο με αποδεκτές αναθεωρήσεις;

 Χρησιμοποιήστε το`Save` μέθοδος του`Document` αντικρούστε να αποθηκεύσετε το τροποποιημένο έγγραφο με αποδεκτές αναθεωρήσεις. Φροντίστε να παρέχετε τη σωστή διαδρομή αρχείου.

```csharp
doc.Save("path/to/the/document.docx");
```

#### Ε: Πώς μπορώ να σταματήσω την παρακολούθηση αναθεωρήσεων στο Aspose.Words για .NET;

 Α: Χρησιμοποιήστε το`StopTrackRevisions` μέθοδος του`Document` αντίρρηση για διακοπή των αναθεωρήσεων παρακολούθησης.

```csharp
doc.StopTrackRevisions();
```

#### Ε: Πώς μπορώ να διαγράψω μια αναθεωρημένη παράγραφο σε ένα έγγραφο με το Aspose.Words για .NET;

 Α: Για να αφαιρέσετε μια αναθεωρημένη παράγραφο σε ένα έγγραφο, μπορείτε να χρησιμοποιήσετε το`Remove` μέθοδος συλλογής παραγράφων.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```