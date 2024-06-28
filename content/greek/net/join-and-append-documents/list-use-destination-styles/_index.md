---
title: Λίστα Χρήση στυλ προορισμού
linktitle: Λίστα Χρήση στυλ προορισμού
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ενώνετε και να προσαρτάτε έγγραφα του Word διατηρώντας τα στυλ λίστας εγγράφων προορισμού χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/join-and-append-documents/list-use-destination-styles/
---

Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία χρήσης της δυνατότητας List Use Destination Styles του Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να ενώνετε και να προσαρτάτε έγγραφα του Word ενώ χρησιμοποιείτε τα στυλ λίστας του εγγράφου προορισμού.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

1. Το Aspose.Words για .NET έχει εγκατασταθεί. Μπορείτε να το κατεβάσετε από τον ιστότοπο Aspose ή να το εγκαταστήσετε μέσω του NuGet.
2. Visual Studio ή οποιοδήποτε άλλο περιβάλλον ανάπτυξης C#.

## Βήμα 1: Αρχικοποιήστε τους Καταλόγους Εγγράφων

 Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο εγγράφων σας. Τροποποιήστε την τιμή του`dataDir` μεταβλητή στη διαδρομή όπου βρίσκονται τα έγγραφά σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε τα έγγραφα προέλευσης και προορισμού

Στη συνέχεια, πρέπει να φορτώσετε τα έγγραφα προέλευσης και προορισμού χρησιμοποιώντας το Aspose.Words.`Document` τάξη. Ενημερώστε τα ονόματα αρχείων στο`Document` κατασκευαστή σύμφωνα με τα ονόματα των εγγράφων σας.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Βήμα 3: Ορίστε το έγγραφο προέλευσης σε Continue μετά το έγγραφο προορισμού

 Για να διασφαλίσετε ότι το περιεχόμενο από το έγγραφο προέλευσης συνεχίζεται μετά το τέλος του εγγράφου προορισμού, πρέπει να ορίσετε το`SectionStart` ιδιότητα της πρώτης ενότητας στο έγγραφο προέλευσης to`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Βήμα 4: Χειριστείτε τη μορφοποίηση λίστας

Για να χειριστείτε τη μορφοποίηση λίστας, θα επαναλάβετε κάθε παράγραφο στο έγγραφο προέλευσης και θα ελέγξετε αν πρόκειται για στοιχείο λίστας. Εάν είναι, θα συγκρίνετε το αναγνωριστικό λίστας με τις υπάρχουσες λίστες στο έγγραφο προορισμού. Εάν υπάρχει λίστα με το ίδιο αναγνωριστικό, θα δημιουργήσετε ένα αντίγραφο της λίστας στο έγγραφο προέλευσης και θα ενημερώσετε τη μορφή λίστας της παραγράφου για να χρησιμοποιήσετε την αντιγραμμένη λίστα.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Βήμα 5: Προσθέστε το έγγραφο προέλευσης στο έγγραφο προορισμού

 Τώρα, μπορείτε να προσθέσετε το έγγραφο προέλευσης στο έγγραφο προορισμού χρησιμοποιώντας το`AppendDocument` μέθοδος του`Document` τάξη. ο`ImportFormatMode.UseDestinationStyles` Η παράμετρος διασφαλίζει ότι τα στυλ λίστας του εγγράφου προορισμού χρησιμοποιούνται κατά τη λειτουργία προσάρτησης.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Βήμα 6: Αποθηκεύστε το τελικό έγγραφο

Τέλος, αποθηκεύστε το συγχωνευμένο έγγραφο με ενεργοποιημένη τη δυνατότητα List Use Destination Styles χρησιμοποιώντας το`Save` μέθοδος του`Document` τάξη.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Παράδειγμα πηγαίου κώδικα για Στυλ προορισμού χρήσης λίστας με χρήση του Aspose.Words για .NET 

Ακολουθεί ο πλήρης πηγαίος κώδικας για τη δυνατότητα "Λίστα Χρήση στυλ προορισμού" σε C# χρησιμοποιώντας Aspose.Words για .NET:


```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Ρυθμίστε το έγγραφο προέλευσης ώστε να συνεχίζει αμέσως μετά το τέλος του εγγράφου προορισμού.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Παρακολουθήστε τις λίστες που δημιουργούνται.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Ελέγξτε εάν το έγγραφο προορισμού περιέχει ήδη μια λίστα με αυτό το αναγνωριστικό. Εάν το κάνει, τότε αυτό μπορεί
			// κάνει τις δύο λίστες να τρέχουν μαζί. Αντ' αυτού, δημιουργήστε ένα αντίγραφο της λίστας στο έγγραφο προέλευσης.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Υπάρχει ήδη μια νέα αντιγραμμένη λίστα για αυτό το αναγνωριστικό, ανακτήστε την αποθηκευμένη λίστα,
				// και χρησιμοποιήστε το στην τρέχουσα παράγραφο.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Προσθέστε ένα αντίγραφο αυτής της λίστας στο έγγραφο και αποθηκεύστε το για μελλοντική αναφορά.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Ορίστε τη λίστα αυτής της παραγράφου στην αντιγραμμένη λίστα.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Προσθέστε το έγγραφο προέλευσης στο τέλος του εγγράφου προορισμού.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Αυτό είναι! Έχετε εφαρμόσει με επιτυχία τη δυνατότητα List Use Destination Styles χρησιμοποιώντας το Aspose.Words για .NET. Το τελικό έγγραφο θα περιέχει το συγχωνευμένο περιεχόμενο με τα στυλ λίστας από το έγγραφο προορισμού.