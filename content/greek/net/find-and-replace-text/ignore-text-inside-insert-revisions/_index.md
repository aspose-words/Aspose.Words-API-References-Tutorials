---
title: Αγνοήστε το κείμενο μέσα στις αναθεωρήσεις εισαγωγής
linktitle: Αγνοήστε το κείμενο μέσα στις αναθεωρήσεις εισαγωγής
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να χρησιμοποιείτε τη δυνατότητα "Ignore Text Inside Insert Revisions" του Aspose.Words για .NET για να χειριστείτε τις αναθεωρήσεις εισαγωγής σε έγγραφα του Word.
type: docs
weight: 10
url: /el/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

Σε αυτό το άρθρο, θα εξερευνήσουμε τον πηγαίο κώδικα C# παραπάνω για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Ignore Text Inside Insert Revisions στη βιβλιοθήκη Aspose.Words για .NET. Αυτή η δυνατότητα είναι χρήσιμη όταν θέλουμε να αγνοήσουμε το κείμενο μέσα στις αναθεωρήσεις εισαγωγής ενώ χειριζόμαστε έγγραφα.

## Προαπαιτούμενα

- Βασικές γνώσεις της γλώσσας C#.
- Περιβάλλον ανάπτυξης .NET με εγκατεστημένη τη βιβλιοθήκη Aspose.Words.

## Βήμα 1: Δημιουργία νέου εγγράφου

 Πριν αρχίσουμε να χειριζόμαστε κείμενο μέσα στις αναθεωρήσεις ένθετων, πρέπει να δημιουργήσουμε ένα νέο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Αυτό μπορεί να γίνει με στιγμιότυπο α`Document` αντικείμενο:

```csharp
Document doc = new Document();
```

## Βήμα 2: Εισαγάγετε κείμενο με παρακολούθηση αναθεωρήσεων

 Μόλις έχουμε ένα έγγραφο, μπορούμε να εισαγάγουμε κείμενο με παρακολούθηση αναθεωρήσεων χρησιμοποιώντας α`DocumentBuilder`αντικείμενο. Για παράδειγμα, για να εισαγάγουμε το κείμενο "Εισάγεται" με παρακολούθηση αναθεωρήσεων, μπορούμε να χρησιμοποιήσουμε το`StartTrackRevisions`, `Writeln` και`StopTrackRevisions` μέθοδοι:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Βήμα 3: Εισαγάγετε κείμενο που δεν έχει ελεγχθεί

 Εκτός από κείμενο με παρακολούθηση αναθεωρήσεων, μπορούμε επίσης να εισάγουμε μη αναθεωρημένο κείμενο χρησιμοποιώντας το`DocumentBuilder` αντικείμενο. Για παράδειγμα, για να εισαγάγουμε το κείμενο "Κείμενο" χωρίς αναθεώρηση, μπορούμε να χρησιμοποιήσουμε το`Write` μέθοδος:

```csharp
builder.Write("Text");
```

## Βήμα 4: Χρήση της συνάρτησης Ignore Text Inside Insert Revisions

 Για να αγνοήσουμε το κείμενο μέσα στις αναθεωρήσεις εισαγωγής σε επόμενες λειτουργίες, μπορούμε να χρησιμοποιήσουμε α`FindReplaceOptions` αντικείμενο και ορίστε το`IgnoreInserted`ιδιοκτησία σε`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Βήμα 5: Χρήση τυπικών εκφράσεων για αναζήτηση και αντικατάσταση

Για να εκτελέσουμε λειτουργίες αναζήτησης και αντικατάστασης στο κείμενο του εγγράφου, θα χρησιμοποιήσουμε κανονικές εκφράσεις. Στο παράδειγμά μας, θα αναζητήσουμε όλες τις εμφανίσεις του γράμματος "e" και θα τις αντικαταστήσουμε με έναν αστερίσκο "* ". Θα χρησιμοποιήσουμε .NET's`Regex` τάξη για αυτό:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Βήμα 6: Προβολή της Εξόδου Τροποποιημένου Εγγράφου

 Αφού εφαρμόσουμε την αναζήτηση και την αντικατάσταση, μπορούμε να εμφανίσουμε το αλλαγμένο περιεχόμενο του εγγράφου χρησιμοποιώντας το`GetText` μέθοδος:

```csharp
Console.WriteLine(doc.GetText());
```

## Βήμα 7: Αλλαγή επιλογών για συμπερίληψη αναθεωρήσεων εισαγωγής

Εάν θέλουμε να συμπεριλάβουμε το κείμενο μέσα στις αναθεωρήσεις εισαγωγής στο αποτέλεσμα εξόδου, μπορούμε να αλλάξουμε τις επιλογές ώστε να μην αγνοούνται οι αναθεωρήσεις εισαγωγής. Για αυτό θα ορίσουμε το`IgnoreInserted`ιδιοκτησία σε`false`:

```csharp
options.IgnoreInserted = false;
```

## Βήμα 8: Προβολή του τροποποιημένου εγγράφου με Εισαγωγή αναθεωρήσεων

Αφού αλλάξουμε τις επιλογές, μπορούμε να εκτελέσουμε την αναζήτηση και να την αντικαταστήσουμε ξανά για να λάβουμε το αποτέλεσμα με το κείμενο μέσα στις αναθεωρήσεις του ένθετου που περιλαμβάνονται:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Παράδειγμα πηγαίου κώδικα για Ignore Text Inside Insert Revisions χρησιμοποιώντας Aspose.Words για .NET

Ακολουθεί το πλήρες δείγμα πηγαίου κώδικα για την επίδειξη της χρήσης της συνάρτησης Ignore Text Inside Insert Revisions με το Aspose.Words για .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Εισαγωγή κειμένου με παρακολούθηση αναθεωρήσεων.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Εισαγωγή μη αναθεωρημένου κειμένου.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## συμπέρασμα

Σε αυτό το άρθρο, εξερευνήσαμε τον πηγαίο κώδικα C# για να κατανοήσουμε πώς να χρησιμοποιήσετε τη συνάρτηση Ignore Text Inside Insert Revisions στο Aspose.Words για .NET. Ακολουθήσαμε έναν βήμα προς βήμα οδηγό για τη δημιουργία ενός εγγράφου, την εισαγωγή κειμένου με παρακολούθηση αναθεωρήσεων και μη αναθεωρημένο κείμενο, χρησιμοποιώντας τη λειτουργία Ignore Text Inside Insert Revisions, εκτέλεση εργασιών αναζήτησης και αντικατάστασης με κανονικές εκφράσεις και εμφάνιση του τροποποιημένου εγγράφου.

### Συχνές ερωτήσεις

#### Ε: Τι είναι η δυνατότητα "Ignore Text Inside Insert Revisions" στο Aspose.Words για .NET;

Α: Η δυνατότητα "Παράβλεψη αναθεωρήσεων εισαγωγής κειμένου" στο Aspose.Words για .NET σάς επιτρέπει να καθορίσετε εάν το κείμενο εντός των αναθεωρήσεων εισαγωγής θα πρέπει να αγνοείται κατά τη διάρκεια ορισμένων λειτουργιών, όπως η εύρεση και η αντικατάσταση κειμένου. Όταν αυτή η δυνατότητα είναι ενεργοποιημένη, το κείμενο μέσα στις αναθεωρήσεις του ένθετου δεν λαμβάνεται υπόψη κατά τη διάρκεια των εργασιών.

#### Ε: Πώς μπορώ να δημιουργήσω ένα νέο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να δημιουργήσετε ένα νέο έγγραφο χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να δημιουργήσετε ένα`Document` αντικείμενο. Ακολουθεί ένα παράδειγμα κώδικα C# για τη δημιουργία ενός νέου εγγράφου:

```csharp
Document doc = new Document();
```

#### Ε: Πώς μπορώ να εισαγάγω κείμενο με παρακολούθηση αναθεωρήσεων στο Aspose.Words για .NET;

Α: Αφού έχετε ένα έγγραφο, μπορείτε να εισαγάγετε κείμενο με παρακολούθηση αναθεωρήσεων χρησιμοποιώντας α`DocumentBuilder` αντικείμενο. Για παράδειγμα, για να εισαγάγετε το κείμενο "Εισάγεται" με παρακολούθηση αναθεωρήσεων, μπορείτε να χρησιμοποιήσετε το`StartTrackRevisions`, `Writeln` , και`StopTrackRevisions` μέθοδοι:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### Ε: Πώς μπορώ να εισαγάγω μη αναθεωρημένο κείμενο στο Aspose.Words για .NET;

 Α: Εκτός από το κείμενο με παρακολούθηση αναθεωρήσεων, μπορείτε επίσης να εισαγάγετε μη αναθεωρημένο κείμενο χρησιμοποιώντας το`DocumentBuilder` αντικείμενο. Για παράδειγμα, για να εισαγάγετε το κείμενο "Κείμενο" χωρίς αναθεώρηση, μπορείτε να χρησιμοποιήσετε το`Write` μέθοδος:

```csharp
builder.Write("Text");
```

#### Ε: Πώς μπορώ να αγνοήσω το κείμενο μέσα στις αναθεωρήσεις εισαγωγής στο Aspose.Words για .NET;

 Α: Για να αγνοήσετε το κείμενο μέσα στις αναθεωρήσεις εισαγωγής κατά τη διάρκεια των επόμενων λειτουργιών, μπορείτε να χρησιμοποιήσετε το α`FindReplaceOptions` αντικείμενο και ορίστε το`IgnoreInserted`ιδιοκτησία σε`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### Ε: Πώς μπορώ να πραγματοποιήσω αναζήτηση και αντικατάσταση χρησιμοποιώντας τυπικές εκφράσεις στο Aspose.Words για .NET;

 Α: Για να εκτελέσετε λειτουργίες αναζήτησης και αντικατάστασης στο κείμενο του εγγράφου χρησιμοποιώντας κανονικές εκφράσεις, μπορείτε να χρησιμοποιήσετε το .NET`Regex` τάξη. Για παράδειγμα, για να αναζητήσετε όλες τις εμφανίσεις του γράμματος "e" και να τις αντικαταστήσετε με έναν αστερίσκο "* ", μπορείτε να δημιουργήσετε ένα`Regex` αντικείμενο και χρησιμοποιήστε το με το`Replace` μέθοδος:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Ε: Πώς μπορώ να δω την τροποποιημένη έξοδο του εγγράφου στο Aspose.Words για .NET;

 Α: Αφού εφαρμόσετε τις λειτουργίες αναζήτησης και αντικατάστασης, μπορείτε να προβάλετε το τροποποιημένο περιεχόμενο του εγγράφου χρησιμοποιώντας το`GetText` μέθοδος:

```csharp
Console.WriteLine(doc.GetText());
```

#### Ε: Πώς μπορώ να συμπεριλάβω τις αναθεωρήσεις του ένθετου στο αποτέλεσμα εξόδου στο Aspose.Words για .NET;

 Α: Για να συμπεριλάβετε το κείμενο μέσα στις αναθεωρήσεις εισαγωγής στο αποτέλεσμα εξόδου, μπορείτε να αλλάξετε τις επιλογές ώστε να μην αγνοούνται οι αναθεωρήσεις εισαγωγής. Για αυτό, μπορείτε να ορίσετε το`IgnoreInserted` ιδιοκτησία του`FindReplaceOptions` αντιτίθεμαι`false`:

```csharp
options.IgnoreInserted = false;
```

#### Ε: Πώς μπορώ να εμφανίσω το τροποποιημένο έγγραφο με τις αναθεωρήσεις του ένθετου στο Aspose.Words για .NET;

Α: Αφού αλλάξετε τις επιλογές για τη συμπερίληψη αναθεωρήσεων εισαγωγής, μπορείτε να εκτελέσετε την αναζήτηση και να την αντικαταστήσετε ξανά για να λάβετε το αποτέλεσμα με το κείμενο που περιλαμβάνεται στις αναθεωρήσεις ένθετου:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```