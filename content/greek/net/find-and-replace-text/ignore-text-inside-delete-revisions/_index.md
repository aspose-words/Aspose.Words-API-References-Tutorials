---
title: Αγνοήστε το κείμενο στο εσωτερικό Διαγραφή αναθεωρήσεων
linktitle: Αγνοήστε το κείμενο στο εσωτερικό Διαγραφή αναθεωρήσεων
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε τη δυνατότητα "Ignore Text Inside Delete Revisions" του Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

Σε αυτό το άρθρο, θα εξερευνήσουμε τον πηγαίο κώδικα C# παραπάνω για να κατανοήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα "Ignore Text Inside Delete Revisions" στη βιβλιοθήκη Aspose.Words για .NET. Αυτή η δυνατότητα είναι χρήσιμη όταν θέλουμε να αγνοήσουμε κείμενο εντός των αναθεωρήσεων διαγραφής κατά την επεξεργασία λέξεων με έγγραφα.

## Επισκόπηση της βιβλιοθήκης Aspose.Words για .NET

Πριν βουτήξω στις λεπτομέρειες του κώδικα, επιτρέψτε μου να παρουσιάσω εν συντομία τη βιβλιοθήκη Aspose.Words για .NET. Είναι μια ισχυρή βιβλιοθήκη που επιτρέπει τη δημιουργία, τροποποίηση και μετατροπή εγγράφων του Word σε εφαρμογές .NET. Προσφέρει πολλές προηγμένες δυνατότητες για επεξεργασία λέξεων με έγγραφα, συμπεριλαμβανομένης της διαχείρισης αναθεωρήσεων.

## Κατανόηση της δυνατότητας "Παράβλεψη κειμένου εντός διαγραφής αναθεωρήσεων".

Η δυνατότητα "Ignore Text Inside Delete Revisions" στο Aspose.Words για .NET σάς επιτρέπει να καθορίσετε εάν το κείμενο μέσα στις αναθεωρήσεις διαγραφής θα πρέπει να αγνοείται κατά τη διάρκεια ορισμένων λειτουργιών, όπως η εύρεση και η αντικατάσταση κειμένου. Όταν αυτή η δυνατότητα είναι ενεργοποιημένη, το διαγραμμένο κείμενο εντός των αναθεωρήσεων δεν λαμβάνεται υπόψη κατά τη διάρκεια των εργασιών.

## Βήμα 1: Δημιουργία νέου εγγράφου χρησιμοποιώντας το Aspose.Words για .NET

 Πριν αρχίσουμε να χειριζόμαστε κείμενο σε ένα έγγραφο, πρέπει να δημιουργήσουμε ένα νέο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Μπορεί να γίνει στιγμιαία α`Document` αντικείμενο:

```csharp
Document doc = new Document();
```

## Βήμα 2: Εισαγωγή μη αναθεωρημένου κειμένου στο έγγραφο

 Μόλις έχουμε ένα έγγραφο, μπορούμε να εισαγάγουμε μη ελεγμένο κείμενο χρησιμοποιώντας το α`DocumentBuilder` αντικείμενο. Για παράδειγμα, για να εισαγάγουμε το κείμενο "Διαγραμμένο κείμενο", μπορούμε να χρησιμοποιήσουμε το`Writeln` και`Write` μέθοδοι:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Βήμα 3: Αφαίρεση παραγράφου με αναθεωρήσεις παρακολούθησης

Για να επεξηγήσουμε τη χρήση της δυνατότητας "Παράβλεψη κειμένου εντός διαγραφής αναθεωρήσεων", θα διαγράψουμε μια παράγραφο από το έγγραφο χρησιμοποιώντας την παρακολούθηση αναθεωρήσεων. Αυτό θα μας επιτρέψει να δούμε πώς αυτή η δυνατότητα επηρεάζει τις επόμενες λειτουργίες.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Βήμα 4: Εφαρμογή της δυνατότητας "Ignore Text Inside Delete Revisions".

 Τώρα που έχουμε προετοιμάσει το έγγραφό μας διαγράφοντας μια παράγραφο, μπορούμε να ενεργοποιήσουμε τη δυνατότητα "Παράβλεψη κειμένου εντός διαγραφής αναθεωρήσεων" χρησιμοποιώντας ένα`FindReplaceOptions` αντικείμενο. Θα ορίσουμε το`IgnoreDeleted`ιδιοκτησία σε`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Βήμα 5: Χρήση τυπικών εκφράσεων για εύρεση και αντικατάσταση

Για να εκτελέσουμε λειτουργίες αναζήτησης και αντικατάστασης στο κείμενο του εγγράφου, θα χρησιμοποιήσουμε κανονικές εκφράσεις. Στο παράδειγμά μας, θα αναζητήσουμε όλες τις εμφανίσεις του γράμματος "e" και θα τις αντικαταστήσουμε με έναν αστερίσκο "* ". .NET`Regex` η τάξη χρησιμοποιείται για αυτό:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Βήμα 6: Εμφάνιση της εξόδου τροποποιημένου εγγράφου

 Αφού εφαρμόσουμε την αναζήτηση και την αντικατάσταση, μπορούμε να εμφανίσουμε το αλλαγμένο περιεχόμενο του εγγράφου χρησιμοποιώντας το`GetText` μέθοδος:

```csharp
Console.WriteLine(doc.GetText());
```

## Βήμα 7: Τροποποίηση των επιλογών για να συμπεριλάβετε διαγραμμένο κείμενο

 Εάν θέλουμε να συμπεριλάβουμε διαγραμμένο κείμενο στο αποτέλεσμα εξόδου, μπορούμε να αλλάξουμε τις επιλογές ώστε να μην αγνοείται το διαγραμμένο κείμενο. Για αυτό θα ορίσουμε το`IgnoreDeleted`ιδιοκτησία σε`false`:

```csharp
options. IgnoreDeleted = false;
```

## Βήμα 8: Εξαγωγή του τροποποιημένου εγγράφου με διαγραμμένο κείμενο

Αφού αλλάξουμε τις επιλογές, μπορούμε να εκτελέσουμε την αναζήτηση και να την αντικαταστήσουμε ξανά για να λάβουμε το αποτέλεσμα με το διαγραμμένο κείμενο να περιλαμβάνεται:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Παράδειγμα πηγαίου κώδικα για Ignore Text Inside Delete Revisions χρησιμοποιώντας Aspose.Words για .NET

Ακολουθεί το πλήρες δείγμα πηγαίου κώδικα για να επιδείξετε τη χρήση της δυνατότητας "Ignore Text Inside Delete Revisions" με το Aspose.Words για .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Εισαγωγή μη αναθεωρημένου κειμένου.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Καταργήστε την πρώτη παράγραφο με αναθεωρήσεις παρακολούθησης.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## συμπέρασμα

Σε αυτό το άρθρο, εξερευνήσαμε τον πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα "Παράβλεψη κειμένου μέσα στη διαγραφή αναθεωρήσεων" στο Aspose.Words για .NET. Αυτή η δυνατότητα είναι χρήσιμη για την παράβλεψη κειμένου εντός των αναθεωρήσεων διαγραφής κατά τον χειρισμό εγγράφων. Ακολουθήσαμε έναν οδηγό βήμα προς βήμα για να δημιουργήσουμε ένα έγγραφο, να εισαγάγουμε κείμενο, να διαγράψουμε μια παράγραφο με παρακολούθηση αναθεωρήσεων, να εφαρμόσουμε τη δυνατότητα "Παράβλεψη κειμένου εντός διαγραφής αναθεωρήσεων" και να εκτελέσουμε λειτουργίες εύρεσης και αντικατάστασης.

### Συχνές ερωτήσεις

#### Ε: Τι είναι η συνάρτηση "Ignore Text Inside Delete Revisions" στο Aspose.Words για .NET;

Α: Η συνάρτηση "Ignore Text Inside Delete Revisions" στο Aspose.Words για .NET σάς επιτρέπει να καθορίσετε εάν το κείμενο εντός των αναθεωρήσεων διαγραφής θα πρέπει να αγνοείται κατά τη διάρκεια ορισμένων λειτουργιών, όπως η εύρεση και η αντικατάσταση κειμένου. Όταν αυτή η δυνατότητα είναι ενεργοποιημένη, το διαγραμμένο κείμενο εντός των αναθεωρήσεων δεν λαμβάνεται υπόψη κατά τη διάρκεια των εργασιών.

#### Ε: Τι είναι το Aspose.Words για .NET;

A: Το Aspose.Words for .NET είναι μια ισχυρή βιβλιοθήκη για τη δημιουργία, την επεξεργασία και τη μετατροπή εγγράφων του Word σε εφαρμογές .NET. Προσφέρει πολλές προηγμένες δυνατότητες για επεξεργασία λέξεων με έγγραφα, συμπεριλαμβανομένης της διαχείρισης αναθεωρήσεων.

#### Ε: Πώς να δημιουργήσετε ένα νέο έγγραφο στο Aspose.Words για .NET;

 Α: Προτού ξεκινήσετε να χειρίζεστε κείμενο σε ένα έγγραφο, πρέπει να δημιουργήσετε ένα νέο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Αυτό μπορεί να γίνει με στιγμιότυπο α`Document` αντικείμενο. Ακολουθεί ένα δείγμα κώδικα για τη δημιουργία ενός νέου εγγράφου:

```csharp
Document doc = new Document();
```

#### Ε: Πώς να εισαγάγετε μη επεξεργασμένο κείμενο σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Αφού έχετε ένα έγγραφο, μπορείτε να εισαγάγετε κείμενο που δεν έχει ελεγχθεί χρησιμοποιώντας ένα`DocumentBuilder` αντικείμενο. Για παράδειγμα, για να εισαγάγετε το κείμενο "Διαγραμμένο κείμενο", μπορείτε να χρησιμοποιήσετε το`Writeln` και`Write` μέθοδοι:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Ε: Πώς μπορώ να διαγράψω μια παράγραφο με παρακολούθηση αναθεωρήσεων στο Aspose.Words για .NET;

Α: Για να επεξηγήσουμε τη χρήση της συνάρτησης "Παράβλεψη κειμένου εντός διαγραφής αναθεωρήσεων", θα διαγράψουμε μια παράγραφο από το έγγραφο χρησιμοποιώντας την παρακολούθηση αναθεωρήσεων. Αυτό θα μας επιτρέψει να δούμε πώς αυτή η λειτουργία επηρεάζει τις επόμενες λειτουργίες.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Ε: Πώς να ενεργοποιήσετε τη δυνατότητα "Ignore Text Inside Delete Revisions" στο Aspose.Words για .NET;

 Α: Τώρα που έχουμε προετοιμάσει το έγγραφό μας διαγράφοντας μια παράγραφο, μπορούμε να ενεργοποιήσουμε τη δυνατότητα "Παράβλεψη κειμένου εντός διαγραφής αναθεωρήσεων" χρησιμοποιώντας ένα`FindReplaceOptions` αντικείμενο. Θα ορίσουμε το`IgnoreDeleted`ιδιοκτησία σε`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Ε: Πώς γίνεται αναζήτηση και αντικατάσταση χρησιμοποιώντας κανονικές εκφράσεις στο Aspose.Words για .NET;

Α: Για να εκτελέσουμε λειτουργίες αναζήτησης και αντικατάστασης στο κείμενο του εγγράφου, θα χρησιμοποιήσουμε τυπικές εκφράσεις. Στο παράδειγμά μας, θα αναζητήσουμε όλες τις εμφανίσεις του γράμματος "e" και θα τις αντικαταστήσουμε με έναν αστερίσκο "* ". Θα χρησιμοποιήσουμε το .NET`Regex` τάξη για αυτό:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Ε: Πώς να προβάλετε το περιεχόμενο του αλλαγμένου εγγράφου στο Aspose.Words για .NET;

Α: Μετά την εφαρμογή της αναζήτησης και αντικατάστασης, μπορούμε να εμφανίσουμε το τροποποιημένο περιεχόμενο του εγγράφου χρησιμοποιώντας το`GetText` μέθοδος:

```csharp
Console.WriteLine(doc.GetText());
```

#### Ε: Πώς να συμπεριλάβετε το διαγραμμένο κείμενο στο αποτέλεσμα εξόδου στο Aspose.Words για .NET;

 Α: Εάν θέλουμε να συμπεριλάβουμε διαγραμμένο κείμενο στο αποτέλεσμα εξόδου, μπορούμε να αλλάξουμε τις επιλογές ώστε να μην αγνοείται το διαγραμμένο κείμενο. Για αυτό, θα ορίσουμε το`IgnoreDeleted`ιδιοκτησία σε`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Ε: Πώς να εμφανίσετε το επεξεργασμένο έγγραφο με διαγραμμένο κείμενο στο Aspose.Words για .NET;

Α: Αφού αλλάξουμε τις επιλογές, μπορούμε να κάνουμε μια νέα αναζήτηση και να την αντικαταστήσουμε για να λάβουμε το αποτέλεσμα με το διαγραμμένο κείμενο να περιλαμβάνεται:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```