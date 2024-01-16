---
title: Διαμόρφωση συνδέσμου προς περιεχόμενο
linktitle: Διαμόρφωση συνδέσμου προς περιεχόμενο
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη ρύθμιση της σύνδεσης με περιεχόμενο σε ένα έγγραφο με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-properties/configuring-link-to-content/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για να ρυθμίσετε τη σύνδεση με περιεχόμενο με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να συνδέσετε με συγκεκριμένο περιεχόμενο σε ένα έγγραφο.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Δημιουργία του εγγράφου και του κατασκευαστή

Σε αυτό το βήμα θα δημιουργήσουμε ένα νέο έγγραφο και θα αρχικοποιήσουμε τον κατασκευαστή. Χρησιμοποιήστε τον παρακάτω κώδικα:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Δημιουργήστε έναν σελιδοδείκτη

Τώρα θα δημιουργήσουμε έναν σελιδοδείκτη στο έγγραφο. Χρησιμοποιήστε τον ακόλουθο κώδικα για να δημιουργήσετε έναν σελιδοδείκτη με κείμενο μέσα:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Αυτός ο κώδικας δημιουργεί έναν σελιδοδείκτη που ονομάζεται "MyBookmark" και προσθέτει κάποιο κείμενο μέσα.

## Βήμα 4: Ρύθμιση του συνδέσμου περιεχομένου

Τώρα θα διαμορφώσουμε τον σύνδεσμο προς το περιεχόμενο χρησιμοποιώντας τις ιδιότητες του εγγράφου. Χρησιμοποιήστε τον ακόλουθο κώδικα για να προσθέσετε και να ανακτήσετε τον σύνδεσμο προς το περιεχόμενο:

```csharp
// Λάβετε τη λίστα με όλες τις προσαρμοσμένες ιδιότητες στο έγγραφο.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Προσθέστε μια ιδιότητα δεσμευμένου περιεχομένου.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Αυτός ο κώδικας προσθέτει μια ιδιότητα που σχετίζεται με το περιεχόμενο που ονομάζεται "Σελιδοδείκτης" με το σελιδοδείκτη "MyBookmark". Στη συνέχεια, ανακτά πληροφορίες ιδιοκτησίας που σχετίζονται με το περιεχόμενο, όπως κατάσταση συνδέσμου, πηγή συνδέσμου και αξία ιδιότητας.

### Παράδειγμα πηγαίου κώδικα για τη ρύθμιση παραμέτρων σύνδεσης προς περιεχόμενο χρησιμοποιώντας το Aspose.Words για .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Ανακτήστε μια λίστα με όλες τις ιδιότητες προσαρμοσμένου εγγράφου από το αρχείο.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Προσθήκη συνδεδεμένου με την ιδιοκτησία περιεχομένου.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Τώρα μάθατε πώς να διαμορφώνετε τη σύνδεση με το περιεχόμενο σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να δημιουργήσετε και να διαμορφώσετε συνδέσμους προς συγκεκριμένο περιεχόμενο στα δικά σας έγγραφα.