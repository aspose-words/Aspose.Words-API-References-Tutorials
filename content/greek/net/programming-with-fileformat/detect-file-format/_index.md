---
title: Ανίχνευση μορφής αρχείου εγγράφου
linktitle: Ανίχνευση μορφής αρχείου εγγράφου
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τον εντοπισμό μορφής αρχείου εγγράφου με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-fileformat/detect-file-format/
---

Αυτό το άρθρο παρέχει έναν οδηγό βήμα προς βήμα σχετικά με τον τρόπο χρήσης της δυνατότητας εντοπισμού μορφής αρχείου εγγράφου με το Aspose.Words για .NET. Θα εξηγήσουμε λεπτομερώς κάθε μέρος του κώδικα. Στο τέλος αυτού του σεμιναρίου, θα μπορείτε να κατανοήσετε πώς να ανιχνεύσετε τη μορφή διαφορετικών αρχείων εγγράφων.

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει τη βιβλιοθήκη Aspose.Words για .NET στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη και τις οδηγίες εγκατάστασης στον ιστότοπο Aspose.

## Βήμα 1: Ορισμός καταλόγων

 Για να ξεκινήσετε, πρέπει να ορίσετε τους καταλόγους στους οποίους θέλετε να αποθηκεύσετε τα αρχεία σύμφωνα με τη μορφή τους. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας. Δημιουργούμε τους καταλόγους "Υποστηριζόμενο", "Άγνωστο", "Κρυπτογραφημένο" και "Pre97" εάν δεν υπάρχουν ήδη.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Δημιουργήστε τους καταλόγους εάν δεν υπάρχουν ήδη.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Βήμα 2: Αναζήτηση αρχείων

 Στη συνέχεια χρησιμοποιούμε το`GetFiles` μέθοδος του`Directory` class για να λάβετε τη λίστα των αρχείων στον καθορισμένο κατάλογο. Χρησιμοποιούμε επίσης α`Where`ρήτρα εξαίρεσης ενός συγκεκριμένου αρχείου με το όνομα "Corrupted document.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Βήμα 3: Εντοπίστε τη μορφή κάθε αρχείου

 Κάνουμε βρόχο σε κάθε αρχείο της λίστας και χρησιμοποιούμε το`DetectFileFormat` μέθοδος του`FileFormatUtil` κλάση για τον εντοπισμό της μορφής του αρχείου. Εμφανίζουμε επίσης τον τύπο εγγράφου που εντοπίστηκε.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Εμφάνιση του τύπου εγγράφου
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... Προσθέστε θήκες για άλλες υποστηριζόμενες μορφές εγγράφων
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

Αυτό είναι όλο ! Εντοπίσατε με επιτυχία τη μορφή διαφορετικών αρχείων εγγράφων χρησιμοποιώντας το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για ανίχνευση μορφής αρχείου με το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Δημιουργήστε τους καταλόγους εάν δεν υπάρχουν ήδη.
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// Εμφάνιση του τύπου εγγράφου
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### Συχνές ερωτήσεις για τον εντοπισμό μορφής αρχείου εγγράφου

#### Πώς να εντοπίσετε τη μορφή ενός αρχείου εγγράφου χρησιμοποιώντας το Aspose.Words για .NET;

 Για να εντοπίσετε τη μορφή ενός αρχείου εγγράφου χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να ακολουθήσετε τα βήματα που παρέχονται στον οδηγό. Χρησιμοποιώντας την`DetectFileFormat` μέθοδος του`FileFormatUtil`class θα σας επιτρέψει να εντοπίσετε τη μορφή του αρχείου εγγράφου. Αυτό θα σας επιτρέψει να προσδιορίσετε εάν πρόκειται για έγγραφο του Microsoft Word 97-2003, πρότυπο, έγγραφο WordprocessingML του Office Open XML ή άλλες υποστηριζόμενες μορφές. Ο κώδικας που παρέχεται στο σεμινάριο θα σας καθοδηγήσει στην εφαρμογή αυτής της δυνατότητας.

#### Ποιες μορφές εγγράφων υποστηρίζει το Aspose.Words for .NET;

Το Aspose.Words for .NET υποστηρίζει μια ποικιλία μορφών εγγράφων, όπως έγγραφα Microsoft Word 97-2003 (DOC), Πρότυπα (DOT), Office Open XML WordprocessingML έγγραφα (DOCX), Office Open XML WordprocessingML έγγραφα με μακροεντολές (DOCM), Office Open Πρότυπα XML WordprocessingML χωρίς μακροεντολές (DOTX), Πρότυπα Office Open XML WordprocessingML με μακροεντολές (DOTM), Επίπεδα έγγραφα OPC, έγγραφα RTF, έγγραφα Microsoft Word 2003 WordprocessingML, έγγραφα HTML, έγγραφα MHTML (αρχειοθέτηση Ιστού), έγγραφα OpenDocument Text (ODT), Πρότυπα OpenDocument Text (OTT), έγγραφα MS Word 6 ή Word 95 και άγνωστες μορφές εγγράφων.

#### Πώς να χειριστείτε κρυπτογραφημένα αρχεία εγγράφων κατά την ανίχνευση μορφής;

 Κατά τον εντοπισμό της μορφής ενός αρχείου εγγράφου, μπορείτε να χρησιμοποιήσετε το`IsEncrypted` ιδιοκτησία του`FileFormatInfo` αντικείμενο για να ελέγξετε εάν το αρχείο είναι κρυπτογραφημένο. Εάν το αρχείο είναι κρυπτογραφημένο, μπορείτε να λάβετε πρόσθετα βήματα για τον χειρισμό αυτής της συγκεκριμένης περίπτωσης, όπως η αντιγραφή του αρχείου σε έναν κατάλογο αφιερωμένο σε κρυπτογραφημένα έγγραφα. Μπορείτε να χρησιμοποιήσετε το`File.Copy` μέθοδο για να γίνει αυτό.

#### Ποιες ενέργειες πρέπει να γίνονται όταν η μορφή ενός εγγράφου είναι άγνωστη;

Όταν η μορφή ενός εγγράφου είναι άγνωστη, μπορείτε να αποφασίσετε να το χειριστείτε με συγκεκριμένο τρόπο για την αίτησή σας. Στο παράδειγμα που παρέχεται στο σεμινάριο, το έγγραφο αντιγράφεται σε έναν συγκεκριμένο κατάλογο αφιερωμένο σε έγγραφα άγνωστης μορφής. Μπορείτε να προσαρμόσετε αυτήν την ενέργεια για να ταιριάζει στις συγκεκριμένες ανάγκες σας.

#### Υπάρχουν άλλες δυνατότητες του Aspose.Words για .NET που μπορούν να χρησιμοποιηθούν σε συνδυασμό με τον εντοπισμό μορφής εγγράφου;

Ναι, το Aspose.Words για .NET προσφέρει πολλές άλλες δυνατότητες για την επεξεργασία και τον χειρισμό εγγράφων του Word. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε τη βιβλιοθήκη για να εξαγάγετε κείμενο, εικόνες ή μεταδεδομένα από έγγραφα, να εφαρμόσετε αλλαγές μορφοποίησης, να συγχωνεύσετε έγγραφα, να μετατρέψετε έγγραφα σε διαφορετικές μορφές και πολλά άλλα.