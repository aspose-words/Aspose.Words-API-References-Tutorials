---
title: Εισαγωγή αντικειμένου Ole στο Word με το πακέτο Ole
linktitle: Εισαγωγή αντικειμένου Ole στο Word με το πακέτο Ole
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να εισάγετε ένα αντικείμενο OLE με ένα πακέτο OLE σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Ακολουθεί ένας αναλυτικός οδηγός για να εξηγήσετε τον πηγαίο κώδικα C# παρακάτω, ο οποίος δείχνει πώς να εισαγάγετε ένα αντικείμενο OLE στο word με ένα πακέτο OLE χρησιμοποιώντας το Aspose.Words για .NET.

## Βήμα 1: Εισαγάγετε τις απαραίτητες αναφορές
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες αναφορές για να χρησιμοποιήσετε το Aspose.Words για .NET στο έργο σας. Αυτό περιλαμβάνει την εισαγωγή της βιβλιοθήκης Aspose.Words και την προσθήκη των απαιτούμενων χώρων ονομάτων στο αρχείο προέλευσης.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Βήμα 2: Δημιουργήστε ένα νέο πρόγραμμα δημιουργίας εγγράφων και εγγράφων
 Σε αυτό το βήμα, θα δημιουργήσουμε ένα νέο έγγραφο χρησιμοποιώντας το`Document` κλάση και ένα πρόγραμμα δημιουργίας εγγράφων χρησιμοποιώντας το`DocumentBuilder` τάξη.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Εισαγάγετε ένα αντικείμενο OLE με ένα πακέτο OLE
 Χρησιμοποιήστε το Document Generator's`InsertOleObject` μέθοδος εισαγωγής ενός αντικειμένου OLE με ένα πακέτο OLE στο έγγραφο. Καθορίστε τη ροή δεδομένων, τον τύπο αντικειμένου, τις επιλογές εμφάνισης και άλλες απαραίτητες ρυθμίσεις.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Βήμα 4: Αποθηκεύστε το έγγραφο
 Χρησιμοποιήστε το έγγραφο`Save` μέθοδο αποθήκευσης του εγγράφου σε αρχείο.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Δείγμα πηγαίου κώδικα για την εισαγωγή ενός αντικειμένου OLE με ένα πακέτο OLE με Aspose.Words για .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Αυτό είναι ένα πλήρες δείγμα κώδικα για την εισαγωγή ενός αντικειμένου OLE με ένα πακέτο OLE με Aspose.Words για .NET. Φροντίστε να εισαγάγετε τις απαραίτητες αναφορές και ακολουθήστε τα βήματα που περιγράφηκαν προηγουμένως για να ενσωματώσετε αυτόν τον κώδικα στο έργο σας.

## συμπέρασμα

Συμπερασματικά, έχουμε ακολουθήσει έναν οδηγό βήμα προς βήμα για την εισαγωγή ενός αντικειμένου OLE σε ένα έγγραφο του Word με ένα πακέτο OLE χρησιμοποιώντας Aspose.Words για .NET.

Ακολουθώντας αυτά τα βήματα, θα μπορείτε να εισαγάγετε με επιτυχία αντικείμενα OLE με πακέτα OLE στα έγγραφά σας του Word χρησιμοποιώντας το Aspose.Words για .NET. Φροντίστε να εισαγάγετε τις απαραίτητες αναφορές και ακολουθήστε προσεκτικά τις οδηγίες για να έχετε τα επιθυμητά αποτελέσματα.

### Συχνές ερωτήσεις για την εισαγωγή αντικειμένου ole στο word με πακέτο ole

#### Ε: Τι διαπιστευτήρια πρέπει να εισαγάγω για να χρησιμοποιήσω το Aspose.Words για .NET;

Α: Για να χρησιμοποιήσετε το Aspose.Words για .NET, πρέπει να εισαγάγετε τις ακόλουθες αναφορές:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Ε: Πώς να δημιουργήσετε ένα νέο έγγραφο και μια δημιουργία εγγράφων;

 Α: Μπορείτε να δημιουργήσετε ένα νέο έγγραφο χρησιμοποιώντας το`Document` κλάση και ένα πρόγραμμα δημιουργίας εγγράφων χρησιμοποιώντας το`DocumentBuilder` τάξη, όπως φαίνεται παρακάτω:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Ε: Πώς να εισαγάγετε ένα αντικείμενο OLE με ένα πακέτο OLE στο έγγραφο;

 Α: Χρησιμοποιήστε το`InsertOleObject`μέθοδος δημιουργίας εγγράφων (`DocumentBuilder`) για να εισαγάγετε ένα αντικείμενο OLE με ένα πακέτο OLE στο έγγραφο. Καθορίστε τη ροή δεδομένων, τον τύπο αντικειμένου, τις επιλογές εμφάνισης και άλλες απαραίτητες ρυθμίσεις. Εδώ είναι ένα παράδειγμα:

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Ε: Πώς να αποθηκεύσετε το έγγραφο;

 Α: Χρησιμοποιήστε το έγγραφο`Save` μέθοδο αποθήκευσης του εγγράφου σε αρχείο. Εδώ είναι ένα παράδειγμα:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Ε: Μπορείτε να δώσετε ένα πλήρες παράδειγμα εισαγωγής αντικειμένου OLE με πακέτο OLE με Aspose.Words για .NET;

Α: Ακολουθεί ένα πλήρες δείγμα κώδικα για την εισαγωγή ενός αντικειμένου OLE με ένα πακέτο OLE χρησιμοποιώντας το Aspose.Words για .NET. Φροντίστε να εισαγάγετε τις απαραίτητες αναφορές και ακολουθήστε τα βήματα που περιγράφηκαν προηγουμένως για να ενσωματώσετε αυτόν τον κώδικα στο έργο σας:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Αυτό ολοκληρώνει το σεμινάριο μας σχετικά με την εισαγωγή ενός αντικειμένου OLE με ένα πακέτο OLE σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Μη διστάσετε να εισαγάγετε τις απαραίτητες αναφορές και ακολουθήστε τα βήματα που περιγράφονται για να ενσωματώσετε αυτόν τον κώδικα στο έργο σας. Εάν έχετε περαιτέρω ερωτήσεις, μη διστάσετε να επικοινωνήσετε μαζί μας.