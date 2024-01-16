---
title: Προτιμώμενος τύπος ελέγχου στο έγγραφο του Word
linktitle: Προτιμώμενος τύπος ελέγχου στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τον καθορισμό του προτιμώμενου τύπου ελέγχου στο έγγραφο του Word κατά τη φόρτωση ενός εγγράφου HTML με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-htmlloadoptions/preferred-control-type/
---
Αυτό το άρθρο παρέχει έναν οδηγό βήμα προς βήμα σχετικά με τον τρόπο χρήσης της δυνατότητας προτιμώμενου τύπου ελέγχου με το Aspose.Words για .NET. Θα εξηγήσουμε λεπτομερώς κάθε μέρος του κώδικα. Στο τέλος αυτού του σεμιναρίου, θα μπορείτε να κατανοήσετε πώς να καθορίσετε τον προτιμώμενο τύπο ελέγχου κατά τη φόρτωση ενός εγγράφου HTML.

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει τη βιβλιοθήκη Aspose.Words για .NET στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη και τις οδηγίες εγκατάστασης στον ιστότοπο Aspose.

## Βήμα 1: Ορίστε τον κώδικα HTML

 Για να ξεκινήσετε, πρέπει να ορίσετε τον κώδικα HTML που θέλετε να φορτώσετε ως έγγραφο. Σε αυτό το παράδειγμα, ορίσαμε ένα`html` μεταβλητή που περιέχει τον κώδικα HTML ενός επιλογέα με επιλογές.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Βήμα 2: Ορίστε τις επιλογές φόρτωσης HTML

 Στη συνέχεια, δημιουργούμε ένα`HtmlLoadOptions` αντικείμενο και ορίστε το`PreferredControlType`ιδιοκτησία σε`HtmlControlType.StructuredDocumentTag`. Αυτό λέει στο Aspose.Words να χρησιμοποιεί StructuredDocumentTags για να αναπαριστά την HTML κατά τη φόρτωση.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Βήμα 3: Φορτώστε και αποθηκεύστε το έγγραφο

 Χρησιμοποιούμε το`Document` κλάση για φόρτωση κώδικα HTML από μια ροή μνήμης με τις επιλογές φόρτωσης που ορίστηκαν προηγουμένως. Στη συνέχεια αποθηκεύουμε το έγγραφο στον καθορισμένο κατάλογο με το`.docx`μορφή αρχείου.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Παράδειγμα πηγαίου κώδικα για τον προτιμώμενο τύπο ελέγχου με Aspose.Words για .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Αυτό είναι όλο ! Έχετε καθορίσει με επιτυχία τον προτιμώμενο τύπο ελέγχου κατά τη φόρτωση ενός εγγράφου HTML με το Aspose.Words για .NET.

## συμπέρασμα

 Ακολουθώντας αυτόν τον αναλυτικό οδηγό, έχετε μάθει πώς να χρησιμοποιείτε τη δυνατότητα "Προτιμώμενος τύπος ελέγχου" στο Aspose.Words για .NET για να καθορίσετε τον επιθυμητό τύπο ελέγχου κατά τη φόρτωση ενός εγγράφου HTML. Ρύθμιση του`PreferredControlType`ιδιοκτησία σε`HtmlControlType.StructuredDocumentTag` επιτρέπει στο Aspose.Words να χρησιμοποιεί StructuredDocumentTags (SDT) για καλύτερη αναπαράσταση και επεξεργασία περιεχομένου HTML. Μπορείτε να εξερευνήσετε και άλλους τύπους ελέγχου για να ταιριάζουν στις συγκεκριμένες απαιτήσεις σας. Η χρήση αυτής της δυνατότητας βοηθά στη διασφάλιση ακριβούς και αποτελεσματικού χειρισμού εγγράφων HTML στην εφαρμογή σας C# με το Aspose.Words.

### Συχνές ερωτήσεις για τον προτιμώμενο τύπο ελέγχου στο έγγραφο του Word

#### Ε: Ποια είναι η δυνατότητα "Προτιμώμενος τύπος ελέγχου" στο Aspose.Words για .NET;

Α: Η δυνατότητα "Προτιμώμενος τύπος ελέγχου" σάς επιτρέπει να καθορίσετε τον προτιμώμενο τύπο ελέγχου για την αναπαράσταση στοιχείων HTML κατά τη φόρτωση ενός εγγράφου HTML. Βοηθά στην επιλογή του κατάλληλου τύπου ελέγχου για καλύτερη αναπαράσταση και επεξεργασία του περιεχομένου HTML.

#### Ε: Πώς μπορώ να ορίσω τον προτιμώμενο τύπο ελέγχου κατά τη φόρτωση ενός εγγράφου HTML;

 Α: Για να ορίσετε τον προτιμώμενο τύπο ελέγχου, πρέπει να δημιουργήσετε ένα`HtmlLoadOptions` αντικείμενο και ορίστε το`PreferredControlType` ιδιοκτησία στο επιθυμητό`HtmlControlType` . Στο παρεχόμενο παράδειγμα,`HtmlControlType.StructuredDocumentTag` χρησιμοποιείται.

#### Ε: Ποια είναι η σημασία της χρήσης StructuredDocumentTags (SDT) ως προτιμώμενου τύπου ελέγχου;

Α: Οι StructuredDocumentTag (SDT) είναι στοιχεία που βασίζονται σε XML που μπορούν να χρησιμοποιηθούν για την αναπαράσταση περίπλοκου περιεχομένου και στοιχείων ελέγχου σε ένα έγγραφο του Word. Η χρήση SDT ως προτιμώμενου τύπου ελέγχου μπορεί να παρέχει καλύτερη συμβατότητα και αναπαράσταση του περιεχομένου HTML.

#### Ε: Πώς μπορώ να διασφαλίσω ότι το Aspose.Words χρησιμοποιεί τον προτιμώμενο τύπο ελέγχου κατά τη φόρτωση του εγγράφου HTML;

 Α: Ρυθμίζοντας το`PreferredControlType`ιδιοκτησία σε`HtmlControlType.StructuredDocumentTag`όπως φαίνεται στο παράδειγμα πηγαίο κώδικα, το Aspose.Words θα χρησιμοποιήσει SDT για να αναπαραστήσει στοιχεία HTML κατά τη φόρτωση του εγγράφου.

#### Ε: Μπορώ να χρησιμοποιήσω άλλους τύπους ελέγχου ως προτιμώμενη επιλογή;

 Α: Ναι, εκτός από`HtmlControlType.StructuredDocumentTag` , Aspose.Words για .NET υποστηρίζει άλλους τύπους ελέγχου όπως`HtmlControlType.ContentControl` και`HtmlControlType.CustomXmlMarkup`.