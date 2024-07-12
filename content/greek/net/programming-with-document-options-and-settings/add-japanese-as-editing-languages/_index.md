---
title: Προσθήκη ιαπωνικών ως γλωσσών επεξεργασίας
linktitle: Προσθήκη ιαπωνικών ως γλωσσών επεξεργασίας
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για την προσθήκη Ιαπωνικών ως γλώσσα επεξεργασίας με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

Σε αυτό το σεμινάριο, θα σας οδηγήσουμε βήμα προς βήμα για να κατανοήσετε και να εφαρμόσετε τη λειτουργικότητα της προσθήκης Ιαπωνικών ως γλώσσας επεξεργασίας με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ορίζετε προτιμήσεις γλώσσας κατά τη φόρτωση ενός εγγράφου και να προσθέτετε τα ιαπωνικά ως γλώσσα επεξεργασίας.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word που δεν περιέχει προεπιλεγμένη γλώσσα επεξεργασίας και στο οποίο θέλουμε να προσθέσουμε ιαπωνικά. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Ορίστε τις προτιμήσεις γλώσσας που θα χρησιμοποιηθούν κατά τη φόρτωση του εγγράφου.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Βήμα 3: Έλεγχος της προεπιλεγμένης γλώσσας

Μετά τη φόρτωση του εγγράφου, θα ελέγξουμε εάν η προεπιλεγμένη γλώσσα επεξεργασίας έχει ρυθμιστεί σωστά στα Ιαπωνικά. Χρησιμοποιήστε τον ακόλουθο κώδικα για να λάβετε το αναγνωριστικό γλώσσας της Άπω Ανατολής:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Ο κωδικός ελέγχει εάν το αναγνωριστικό γλώσσας της Άπω Ανατολής ταιριάζει με αυτό των Ιαπωνικών. Σύμφωνα με το αποτέλεσμα, εμφανίζει ένα αντίστοιχο μήνυμα.

### Παράδειγμα πηγαίου κώδικα για Προσθήκη ιαπωνικών ως γλωσσών επεξεργασίας χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Ορίστε τις προτιμήσεις γλώσσας που θα χρησιμοποιούνται κατά τη φόρτωση του εγγράφου.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

