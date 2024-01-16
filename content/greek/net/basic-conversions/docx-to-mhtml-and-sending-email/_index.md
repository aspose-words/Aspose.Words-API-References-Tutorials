---
title: Μετατροπή Docx σε Mhtml και αποστολή email
linktitle: Μετατροπή Docx σε Mhtml και αποστολή email
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να μετατρέπετε έγγραφα του Word από Docx σε MHTML και να τα στέλνετε ως email χρησιμοποιώντας τα Aspose.Words και Aspose.Email. Βήμα προς βήμα φροντιστήριο.
type: docs
weight: 10
url: /el/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

Σε αυτό το βήμα προς βήμα σεμινάριο, θα σας καθοδηγήσουμε πώς να χρησιμοποιήσετε το Aspose.Words για .NET για να μετατρέψετε ένα έγγραφο Word σε μορφή Docx σε MHTML και να το στείλετε ως email χρησιμοποιώντας το Aspose.Email. Θα εξηγήσουμε τον παρεχόμενο πηγαίο κώδικα C# και θα σας δείξουμε πώς να τον εφαρμόσετε στα δικά σας έργα.

 Για να ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τις βιβλιοθήκες Aspose.Words για .NET και Aspose.Email στο περιβάλλον ανάπτυξης σας. Εάν δεν το έχετε κάνει, κατεβάστε και εγκαταστήστε τις βιβλιοθήκες από[Aspose.Απαλλαγές](https://releases.aspose.com/words/net/).

## Βήμα 1: Αρχικοποίηση του αντικειμένου εγγράφου

 Αρχικά, αρχικοποιήστε το`Document`αντικείμενο με τη διαδρομή προς το έγγραφο προέλευσης σε μορφή Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Βήμα 2: Αποθήκευση του εγγράφου σε μορφή MHTML

 Στη συνέχεια, αποθηκεύστε το έγγραφο στο a`Stream` αντικείμενο σε μορφή MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Βήμα 3: Επαναφορά της ροής

Εφόσον το Aspose.Email πρέπει να διαβάσει τη ροή από την αρχή, επαναφέρετε τη ροή στην αρχή:

```csharp
stream.Position = 0;
```

## Βήμα 4: Δημιουργία μηνύματος MIME Aspose.Email

 Δημιουργώ ένα`MailMessage` αντικείμενο από τη ροή χρησιμοποιώντας`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Μη διστάσετε να προσαρμόσετε τις ιδιότητες του μηνύματος, όπως ο αποστολέας, ο παραλήπτης και το θέμα.

## Βήμα 5: Αποστολή email

 Χρησιμοποιήστε το Aspose.Email's`SmtpClient` για να στείλετε το email:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Βεβαιωθείτε ότι παρέχετε τη σωστή διεύθυνση κεντρικού υπολογιστή διακομιστή SMTP.

Αυτό είναι! Μετατρέψατε επιτυχώς ένα έγγραφο του Word σε μορφή Docx σε MHTML και το στείλατε ως email χρησιμοποιώντας το Aspose.Words για .NET και Aspose.Email.

### Παράδειγμα πηγαίου κώδικα για Docx σε Mhtml και αποστολή email χρησιμοποιώντας Aspose.Words για .NET

```csharp

	// Document doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Κάντε επαναφορά της ροής στην αρχή, ώστε το Aspose.Email να μπορεί να το διαβάσει.
	stream.Position = 0;

	// Δημιουργήστε ένα μήνυμα ηλεκτρονικού ταχυδρομείου Aspose.Email MIME από τη ροή.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Στείλτε το μήνυμα χρησιμοποιώντας το Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Μη διστάσετε να χρησιμοποιήσετε αυτόν τον κωδικό στα δικά σας έργα και να τον τροποποιήσετε σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.

### Συχνές ερωτήσεις

#### Πώς να μετατρέψετε ένα αρχείο DOCX σε MHTML;

Για να μετατρέψετε ένα αρχείο DOCX σε MHTML, μπορείτε να χρησιμοποιήσετε εργαλεία λογισμικού ή βιβλιοθήκες που παρέχουν αυτήν τη λειτουργία. Το Aspose.Words για .NET είναι μια αξιόπιστη επιλογή για αυτήν τη μετατροπή. Μπορείτε να χρησιμοποιήσετε το API της βιβλιοθήκης για να φορτώσετε το αρχείο DOCX και να το αποθηκεύσετε σε μορφή MHTML.

#### Πώς μπορώ να στείλω ένα email με συνημμένο αρχείο MHTML;

Για να στείλετε ένα email με ένα αρχείο MHTML ως συνημμένο, μπορείτε να χρησιμοποιήσετε βιβλιοθήκες ή εργαλεία ειδικά για την αποστολή email, όπως το System.Net.Mail στο .NET. Πρέπει να δημιουργήσετε ένα μήνυμα email, να καθορίσετε τον παραλήπτη, το θέμα και το περιεχόμενο και, στη συνέχεια, να προσθέσετε το αρχείο MHTML ως συνημμένο στο μήνυμα πριν το στείλετε.

#### Ποιοι είναι οι περιορισμοί της διαδικασίας μετατροπής και αποστολής email;

Οι περιορισμοί της διαδικασίας μετατροπής και αποστολής email εξαρτώνται από τα συγκεκριμένα εργαλεία που χρησιμοποιείτε. Ορισμένα εργαλεία ενδέχεται να έχουν περιορισμούς που σχετίζονται με το μέγεθος του αρχείου, τις ρυθμίσεις ασφαλείας ή τα υποστηριζόμενα πρωτόκολλα email. Είναι σημαντικό να επιλέξετε εργαλεία που ταιριάζουν στις ανάγκες σας και να λάβετε υπόψη αυτούς τους περιορισμούς κατά την εφαρμογή.

#### Είναι το Aspose ένα αξιόπιστο εργαλείο για τη μετατροπή DOCX σε MHTML και την αποστολή email;

Ναι, το Aspose.Words για .NET είναι ένα αξιόπιστο εργαλείο για τη μετατροπή DOCX σε MHTML και την αποστολή email. Χρησιμοποιείται ευρέως από προγραμματιστές και επαγγελματίες για την απόδοση και την ποιότητά του. Το εργαλείο προσφέρει ολοκληρωμένη τεκμηρίωση, προηγμένες δυνατότητες και αποκλειστική τεχνική υποστήριξη, καθιστώντας το μια συνιστώμενη επιλογή για αυτές τις εργασίες.