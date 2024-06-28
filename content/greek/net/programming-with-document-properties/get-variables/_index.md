---
title: Λήψη μεταβλητών
linktitle: Λήψη μεταβλητών
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την ανάκτηση μεταβλητών εγγράφων με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-properties/get-variables/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να ανακτήσετε μεταβλητές από ένα έγγραφο με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να έχετε πρόσβαση σε μεταβλητές που ορίζονται σε ένα έγγραφο.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word από το οποίο θέλουμε να ανακτήσουμε τις μεταβλητές. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Ανάκτηση μεταβλητών

Τώρα θα ανακτήσουμε τις μεταβλητές που ορίζονται στο έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Αυτός ο κώδικας επαναλαμβάνεται σε κάθε ζεύγος κλειδιού-τιμής στις μεταβλητές εγγράφου και ανακτά το όνομα και την τιμή κάθε μεταβλητής. Στη συνέχεια, οι μεταβλητές συνδέονται για να εμφανίσουν τις πληροφορίες για κάθε μεταβλητή.

### Παράδειγμα πηγαίου κώδικα για Λήψη μεταβλητών χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα έχετε μάθει πώς να ανακτάτε μεταβλητές από ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να αποκτήσετε πρόσβαση και να προβάλετε μεταβλητές από τα δικά σας έγγραφα.