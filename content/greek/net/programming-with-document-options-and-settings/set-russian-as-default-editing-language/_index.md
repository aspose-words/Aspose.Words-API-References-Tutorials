---
title: Ορίστε τα ρωσικά ως προεπιλεγμένη γλώσσα επεξεργασίας
linktitle: Ορίστε τα ρωσικά ως προεπιλεγμένη γλώσσα επεξεργασίας
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για να ορίσετε τα ρωσικά ως την προεπιλεγμένη γλώσσα επεξεργασίας ενός εγγράφου με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα της C# για να ορίσετε τα ρωσικά ως την προεπιλεγμένη γλώσσα επεξεργασίας με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ορίσετε την προεπιλεγμένη γλώσσα κατά τη φόρτωση ενός εγγράφου.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Φόρτωση του εγγράφου

Σε αυτό το βήμα, θα φορτώσουμε το έγγραφο του Word για το οποίο θέλουμε να ορίσουμε τα ρωσικά ως προεπιλεγμένη γλώσσα επεξεργασίας. Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το έγγραφο:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή του καταλόγου όπου βρίσκεται το έγγραφό σας.

## Βήμα 3: Έλεγχος της προεπιλεγμένης γλώσσας

Μετά τη μεταφόρτωση του εγγράφου, θα ελέγξουμε εάν η προεπιλεγμένη γλώσσα έχει ρυθμιστεί σωστά στα Ρωσικά. Χρησιμοποιήστε τον ακόλουθο κώδικα για να λάβετε το προεπιλεγμένο αναγνωριστικό γλώσσας:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Ο κωδικός ελέγχει εάν το αναγνωριστικό γλώσσας ταιριάζει με αυτό των ρωσικών. Σύμφωνα με το αποτέλεσμα, εμφανίζει ένα αντίστοιχο μήνυμα.

### Παράδειγμα πηγαίου κώδικα για Ορισμός ρωσικών ως προεπιλεγμένης γλώσσας επεξεργασίας χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή εγγράφου στο`dataDir` μεταβλητός.

Τώρα μάθατε πώς να ορίζετε τα ρωσικά ως την προεπιλεγμένη γλώσσα επεξεργασίας για ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βημάτων