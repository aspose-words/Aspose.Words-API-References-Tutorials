---
title: Επανεκκίνηση Αριθμός λίστας
linktitle: Επανεκκίνηση Αριθμός λίστας
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να επαναφέρετε τον αριθμό μιας λίστας σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-list/restart-list-number/
---
Σε αυτό το βήμα προς βήμα σεμινάριο, θα σας δείξουμε πώς να επαναφέρετε τον αριθμό μιας λίστας σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Θα εξηγήσουμε τον παρεχόμενο πηγαίο κώδικα C# και θα σας δείξουμε πώς να τον εφαρμόσετε στα δικά σας έργα.

 Για να ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει το Aspose.Words για .NET στο περιβάλλον ανάπτυξης σας. Εάν δεν το έχετε κάνει ήδη, κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από[Aspose.Releases]https://releases.aspose.com/words/net/.

## Βήμα 1: Δημιουργία του Εγγράφου και της Δημιουργίας Εγγράφων

Αρχικά, δημιουργήστε ένα νέο έγγραφο και μια σχετική δημιουργία εγγράφων:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 2: Δημιουργία και προσαρμογή της πρώτης λίστας

Στη συνέχεια, δημιουργήστε μια λίστα με βάση ένα υπάρχον πρότυπο και, στη συνέχεια, προσαρμόστε τα επίπεδά του:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Βήμα 3: Προσθήκη στοιχείων στην πρώτη λίστα

Χρησιμοποιήστε το εργαλείο δημιουργίας εγγράφων για να προσθέσετε στοιχεία στην πρώτη λίστα και να καταργήσετε αριθμούς λίστας:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Βήμα 4: Δημιουργία και προσαρμογή της δεύτερης λίστας

Για να χρησιμοποιήσετε ξανά την πρώτη λίστα επαναφέροντας τον αριθμό, δημιουργήστε ένα αντίγραφο της αρχικής διάταξης λίστας:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Μπορείτε επίσης να κάνετε πρόσθετες αλλαγές στη δεύτερη λίστα εάν χρειάζεται.

## Βήμα 5: Προσθήκη στοιχείων στη δεύτερη λίστα

Χρησιμοποιήστε ξανά το εργαλείο δημιουργίας εγγράφων για να προσθέσετε στοιχεία στη δεύτερη λίστα και να αφαιρέσετε τους αριθμούς λίστας:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Βήμα 6: Αποθηκεύστε το τροποποιημένο έγγραφο

Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Ετσι ! Έχετε επαναφέρει επιτυχώς τον αριθμό μιας λίστας σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.

### Δείγμα πηγαίου κώδικα για επαναφορά αριθμού λίστας

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Δημιουργήστε μια λίστα με βάση ένα πρότυπο.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Για να επαναχρησιμοποιήσουμε την πρώτη λίστα, πρέπει να επανεκκινήσουμε την αρίθμηση δημιουργώντας ένα αντίγραφο της αρχικής μορφοποίησης της λίστας.
List list2 = doc.Lists.AddCopy(list1);

// Μπορούμε να τροποποιήσουμε τη νέα λίστα με οποιονδήποτε τρόπο, συμπεριλαμβανομένου του ορισμού ενός νέου αριθμού έναρξης.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να επανεκκινήσω την αρίθμηση μιας λίστας στο Aspose.Words;

 Α: Για να επανεκκινήσετε την αρίθμηση μιας λίστας στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`ListRestartAtNumber` μέθοδος του`List` τάξη. Αυτή η μέθοδος σάς επιτρέπει να ορίσετε μια νέα τιμή κλήσης από την οποία θα πρέπει να γίνει επανεκκίνηση της λίστας. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε`list.ListRestartAtNumber(1)` για επανεκκίνηση της αρίθμησης από το 1.

#### Ε: Είναι δυνατόν να προσαρμόσετε το πρόθεμα και το επίθημα της επανεκκινημένης αρίθμησης λιστών στο Aspose.Words;

 Α: Ναι, μπορείτε να προσαρμόσετε το πρόθεμα και το επίθημα της επανεκκινημένης αρίθμησης λιστών στο Aspose.Words. ο`ListLevel` η κλάση προσφέρει ιδιότητες όπως`ListLevel.NumberPrefix` και`ListLevel.NumberSuffix` που σας επιτρέπουν να καθορίσετε το πρόθεμα και το επίθημα για κάθε επίπεδο στη λίστα. Μπορείτε να χρησιμοποιήσετε αυτές τις ιδιότητες για να προσαρμόσετε το πρόθεμα και το επίθημα όπως απαιτείται.

#### Ε: Πώς μπορώ να καθορίσω μια συγκεκριμένη τιμή αρίθμησης από την οποία θα πρέπει να γίνει επανεκκίνηση της λίστας;

Α: Για να καθορίσετε μια συγκεκριμένη αριθμητική τιμή από την οποία θα πρέπει να γίνει επανεκκίνηση της λίστας, μπορείτε να χρησιμοποιήσετε το`ListRestartAtNumber` μέθοδος που μεταβιβάζει την επιθυμητή τιμή ως όρισμα. Για παράδειγμα, για να επανεκκινήσετε την αρίθμηση από το 5, μπορείτε να χρησιμοποιήσετε`list.ListRestartAtNumber(5)`.

#### Ε: Είναι δυνατή η επανεκκίνηση της αρίθμησης λιστών πολλαπλών επιπέδων στο Aspose.Words;

 Α: Ναι, το Aspose.Words υποστηρίζει επανεκκίνηση αρίθμησης πολλαπλών επιπέδων λίστας. Μπορείτε να εφαρμόσετε το`ListRestartAtNumber` μέθοδος σε κάθε επίπεδο λίστας για επανεκκίνηση της αρίθμησης ξεχωριστά. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε`list.Levels[0].ListRestartAtNumber(1)` για επανεκκίνηση του πρώτου επιπέδου λίστας από το 1 και`list.Levels[1].ListRestartAtNumber(1)` για επανεκκίνηση της λίστας δεύτερου επιπέδου ξεκινώντας από το 1 και ούτω καθεξής.



