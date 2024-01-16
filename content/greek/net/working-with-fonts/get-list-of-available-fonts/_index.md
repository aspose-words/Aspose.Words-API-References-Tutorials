---
title: Λήψη λίστας διαθέσιμων γραμματοσειρών
linktitle: Λήψη λίστας διαθέσιμων γραμματοσειρών
second_title: Aspose.Words Document Processing API
description: Σε αυτό το σεμινάριο, μάθετε πώς να λαμβάνετε τη λίστα με τις γραμματοσειρές που είναι διαθέσιμες στο Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fonts/get-list-of-available-fonts/
---
Σε αυτό το σεμινάριο, θα εξηγήσουμε πώς να αποκτήσετε τη λίστα με τις γραμματοσειρές που είναι διαθέσιμες στο Aspose.Words για .NET. Η λίστα με τις διαθέσιμες γραμματοσειρές σάς επιτρέπει να γνωρίζετε ποιες γραμματοσειρές μπορείτε να χρησιμοποιήσετε στα έγγραφά σας. Θα σας οδηγήσουμε βήμα προς βήμα για να σας βοηθήσουμε να κατανοήσετε και να εφαρμόσετε τον κώδικα στο έργο σας .NET.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα στοιχεία:
- Γνώση εργασίας της γλώσσας προγραμματισμού C#
- Η βιβλιοθήκη Aspose.Words για .NET είναι εγκατεστημένη στο έργο σας

## Βήμα 1: Ορίστε τον κατάλογο εγγράφων
 Αρχικά, πρέπει να ορίσετε τη διαδρομή καταλόγου στη θέση του εγγράφου του Word. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στον κωδικό με την κατάλληλη διαδρομή.

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Διαμόρφωση πηγών γραμματοσειράς
 Στη συνέχεια, θα δημιουργήσουμε ένα παράδειγμα του`FontSettings` και λάβετε τις υπάρχουσες πηγές γραμματοσειράς χρησιμοποιώντας το`GetFontsSources()` μέθοδος. Θα προσθέσουμε επίσης μια νέα πηγή γραμματοσειράς καθορίζοντας έναν φάκελο που περιέχει γραμματοσειρές.

```csharp
// Διαμόρφωση πηγών γραμματοσειράς
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Προσθήκη νέας πηγής γραμματοσειράς
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Βήμα 3: Λάβετε τη λίστα με τις διαθέσιμες γραμματοσειρές
 Τώρα θα περιηγηθούμε στις διαθέσιμες γραμματοσειρές χρησιμοποιώντας το`GetAvailableFonts()` μέθοδος στην πρώτη ενημερωμένη πηγή γραμματοσειράς.

```csharp
// Λάβετε τη λίστα με τις διαθέσιμες γραμματοσειρές
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Δείγμα πηγαίου κώδικα για Λήψη λίστας διαθέσιμων γραμματοσειρών χρησιμοποιώντας το Aspose.Words για .NET 

```csharp

// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Προσθέστε μια νέα πηγή φακέλου που θα δώσει εντολή στο Aspose.Words να αναζητήσει γραμματοσειρές στον παρακάτω φάκελο.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Προσθέστε τον προσαρμοσμένο φάκελο που περιέχει τις γραμματοσειρές μας στη λίστα με τις υπάρχουσες πηγές γραμματοσειρών.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## συμπέρασμα
Σε αυτό το σεμινάριο, είδαμε πώς να λάβετε τη λίστα με τις γραμματοσειρές που είναι διαθέσιμες στο Aspose.Words για .NET. Αυτό σας επιτρέπει να γνωρίζετε ποιες γραμματοσειρές μπορείτε να χρησιμοποιήσετε στα έγγραφά σας. Μη διστάσετε να χρησιμοποιήσετε αυτήν τη δυνατότητα για να επιλέξετε τις κατάλληλες γραμματοσειρές για τις ανάγκες σας.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να ανακτήσω τη λίστα με τις γραμματοσειρές που είναι διαθέσιμες στο Aspose.Words;

 Α: Για να ανακτήσετε τη λίστα με τις γραμματοσειρές που είναι διαθέσιμες στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`FontsProvider` τάξη και το`GetAvailableFonts` μέθοδος. Αυτή η μέθοδος θα επιστρέψει μια λίστα με όλες τις γραμματοσειρές που είναι εγκατεστημένες στο σύστημά σας.

#### Ε: Μπορώ να φιλτράρω τη λίστα με τις διαθέσιμες γραμματοσειρές με συγκεκριμένα κριτήρια στο Aspose.Words;

Α: Ναι, μπορείτε να φιλτράρετε τη λίστα με τις διαθέσιμες γραμματοσειρές στο Aspose.Words χρησιμοποιώντας συγκεκριμένα κριτήρια. Για παράδειγμα, μπορείτε να φιλτράρετε τις γραμματοσειρές κατά οικογένεια, στυλ ή γλώσσα.

#### Ε: Πώς μπορώ να χρησιμοποιήσω τη λίστα με τις διαθέσιμες γραμματοσειρές στα έγγραφα του Word;

 Α: Για να χρησιμοποιήσετε τη λίστα με τις διαθέσιμες γραμματοσειρές στα έγγραφα του Word, μπορείτε να περιηγηθείτε στη λίστα και να επιλέξετε τις κατάλληλες γραμματοσειρές χρησιμοποιώντας τις μεθόδους και τις ιδιότητες του`FontSettings` τάξη στο Aspose.Λέξεις.