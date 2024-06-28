---
title: Αλλαγή Πηγής πολιτισμού ενημέρωσης πεδίου
linktitle: Αλλαγή Πηγής πολιτισμού ενημέρωσης πεδίου
second_title: Aspose.Words Document Processing API
description: Αλλαγή πηγής πολιτισμού ενημέρωσης πεδίου, οδηγός βήμα προς βήμα για την τροποποίηση της πηγής πολιτισμού στο Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fields/change-field-update-culture-source/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία αλλαγής της πηγής πολιτισμού ενημέρωσης πεδίου σε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET. Τροποποιώντας την πηγή πολιτισμού, μπορείτε να ελέγξετε τη μορφοποίηση της ημερομηνίας κατά την ενημέρωση πεδίου και τις λειτουργίες συγχώνευσης αλληλογραφίας. Θα σας παρέχουμε τον απαραίτητο πηγαίο κώδικα C# και οδηγίες βήμα προς βήμα για να το πετύχετε.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Η βιβλιοθήκη Aspose.Words for .NET είναι εγκατεστημένη στο σύστημά σας.

## Βήμα 1: Δημιουργήστε ένα Document and DocumentBuilder
Για να ξεκινήσετε, δημιουργήστε μια παρουσία της κλάσης Document και ένα αντικείμενο DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 2: Εισαγάγετε περιεχόμενο με συγκεκριμένες τοπικές ρυθμίσεις
Στη συνέχεια, ορίστε την τοπική ρύθμιση στα Γερμανικά και εισαγάγετε πεδία με μορφοποίηση ημερομηνίας:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Στον παραπάνω κώδικα, ορίσαμε την τοπική γλώσσα γραμματοσειράς στα Γερμανικά (Local ID 1031) και εισάγουμε δύο πεδία με συγκεκριμένη μορφοποίηση ημερομηνίας.

## Βήμα 3: Αλλάξτε την πηγή πολιτισμού ενημέρωσης πεδίου
Για να αλλάξετε την πηγή πολιτισμού ενημέρωσης πεδίου, χρησιμοποιήστε την κλάση FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

Σε αυτό το παράδειγμα, ορίσαμε την καλλιέργεια που χρησιμοποιείται κατά την ενημέρωση πεδίου να επιλέγεται από την καλλιέργεια που χρησιμοποιείται από το πεδίο.

## Βήμα 4: Εκτελέστε συγχώνευση αλληλογραφίας
Εκτελέστε μια λειτουργία συγχώνευσης αλληλογραφίας και καθορίστε την τιμή ημερομηνίας για το πεδίο "Ημερομηνία2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

Σε αυτό το απόσπασμα κώδικα, εκτελούμε τη λειτουργία συγχώνευσης αλληλογραφίας και παρέχουμε μια τιμή DateTime για το πεδίο "Date2".

## Βήμα 5: Αποθηκεύστε το έγγραφο
Αποθηκεύστε το τροποποιημένο έγγραφο σε ένα αρχείο χρησιμοποιώντας τη μέθοδο Save της κλάσης Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Παράδειγμα πηγαίου κώδικα για αλλαγή της πηγής πολιτισμού ενημέρωσης πεδίου χρησιμοποιώντας το Aspose.Words για .NET
Ακολουθεί ο πλήρης πηγαίος κώδικας για την αλλαγή της πηγής πολιτισμού ενημέρωσης πεδίου σε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## συμπέρασμα
Συγχαρητήρια! Μάθατε με επιτυχία πώς να αλλάξετε την πηγή πολιτισμού ενημέρωσης πεδίου σε έγγραφα του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα, μπορείτε τώρα να ελέγξετε την κουλτούρα που χρησιμοποιείται για τη μορφοποίηση ημερομηνίας κατά τις λειτουργίες ενημέρωσης πεδίου και συγχώνευσης αλληλογραφίας. Προσαρμόστε την πηγή πολιτισμού σύμφωνα με τις απαιτήσεις σας για να εξασφαλίσετε ακριβή και συνεπή ημερομηνία.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να αλλάξω την πηγή πολιτισμού ενημέρωσης πεδίου στο Aspose.Words για .NET;

 Α: Για να αλλάξετε την πηγή πολιτισμού ενημέρωσης πεδίου στο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Document.FieldOptions.CultureSource` ιδιοκτησία και ορίστε την τιμή του σε`FieldCultureSource.FieldCode` ή`FieldCultureSource.CurrentThread` . Για παράδειγμα, μπορείτε να χρησιμοποιήσετε`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` για να χρησιμοποιήσετε την κουλτούρα που ορίζεται στον κωδικό πεδίου.

#### Ε: Πώς μπορώ να καθορίσω μια συγκεκριμένη κουλτούρα για την ενημέρωση πεδίων στο Aspose.Words για .NET;

 Α: Για να καθορίσετε μια συγκεκριμένη κουλτούρα για την ενημέρωση πεδίων στο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Document.FieldOptions.FieldUpdateCultureInfo` ιδιοκτησία και ορίστε το`CultureInfo` αντικείμενο που αντιστοιχεί στον επιθυμητό πολιτισμό. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` για να προσδιορίσει τη γαλλική (Γαλλία) κουλτούρα.

#### Ε: Είναι δυνατόν να απενεργοποιήσετε την αυτόματη ενημέρωση πεδίων στο Aspose.Words για .NET;

 Α: Ναι, είναι δυνατό να απενεργοποιήσετε την αυτόματη ενημέρωση πεδίων στο Aspose.Words για .NET. Μπορείτε να χρησιμοποιήσετε το`Document.FieldOptions.UpdateFields` ιδιοκτησία και ρυθμίστε το σε`false` για να αποτρέψετε την αυτόματη ενημέρωση των πεδίων. Αυτό σας επιτρέπει να ελέγχετε χειροκίνητα την ενημέρωση των πεδίων όπως απαιτείται.

#### Ε: Πώς μπορώ να ενημερώσω μη αυτόματα τα πεδία εγγράφων στο Aspose.Words για .NET;

 Α: Για μη αυτόματη ενημέρωση πεδίων σε ένα έγγραφο στο Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε το`Field.Update` μέθοδος για κάθε πεδίο ξεχωριστά. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε`field.Update()` για ενημέρωση του συγκεκριμένου πεδίου.