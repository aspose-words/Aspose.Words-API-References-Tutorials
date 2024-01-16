---
title: Λήψη αντικατάστασης χωρίς επιθήματα
linktitle: Λήψη αντικατάστασης χωρίς επιθήματα
second_title: Aspose.Words Document Processing API
description: Σε αυτό το σεμινάριο, μάθετε πώς να λαμβάνετε αντικαταστάσεις χωρίς επιθήματα σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-fonts/get-substitution-without-suffixes/
---

Σε αυτό το σεμινάριο, θα σας δείξουμε πώς να λαμβάνετε τις παρακάμψεις χωρίς επιθήματα σε ένα έγγραφο του Word χρησιμοποιώντας τη βιβλιοθήκη Aspose.Words για .NET. Οι αντικαταστάσεις χωρίς επιθέματα χρησιμοποιούνται για την επίλυση προβλημάτων αντικατάστασης γραμματοσειράς κατά την εμφάνιση ή την εκτύπωση εγγράφων. Θα σας οδηγήσουμε βήμα προς βήμα για να σας βοηθήσουμε να κατανοήσετε και να εφαρμόσετε τον κώδικα στο έργο σας .NET.

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

## Βήμα 2: Φορτώστε το έγγραφο και διαμορφώστε τις αντικαταστάσεις χωρίς επιθήματα
 Στη συνέχεια, θα φορτώσουμε το έγγραφο χρησιμοποιώντας το`Document` κλάση και διαμόρφωση αντικαταστάσεων χωρίς επίθημα χρησιμοποιώντας το`DocumentSubstitutionWarnings` τάξη. Θα προσθέσουμε επίσης μια πηγή γραμματοσειράς καθορίζοντας έναν φάκελο που περιέχει τις γραμματοσειρές.

```csharp
// Φορτώστε το έγγραφο και διαμορφώστε τις αντικαταστάσεις χωρίς επιθήματα
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Βήμα 3: Αποθηκεύστε το έγγραφο
Τέλος, θα αποθηκεύσουμε το έγγραφο με τις παρακάμψεις χωρίς επίθημα.

```csharp
// Αποθηκεύστε το έγγραφο
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Δείγμα πηγαίου κώδικα για Λήψη αντικατάστασης χωρίς επιθήματα χρησιμοποιώντας Aspose.Words για .NET 
```csharp

// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## συμπέρασμα
Σε αυτό το σεμινάριο, είδαμε πώς να λαμβάνετε τις παρακάμψεις χωρίς επιθήματα σε ένα έγγραφο του Word με το Aspose.Words για .NET. Οι αντικαταστάσεις χωρίς επιθέματα είναι χρήσιμες για την επίλυση προβλημάτων αντικατάστασης γραμματοσειράς. Μη διστάσετε να χρησιμοποιήσετε αυτήν τη δυνατότητα για να βελτιώσετε την εμφάνιση και την εκτύπωση των εγγράφων σας.

### Συχνές ερωτήσεις

#### Ε: Γιατί το Aspose.Words προσθέτει επιθήματα σε αντικαταστάσεις γραμματοσειρών;

Α: Το Aspose.Words προσθέτει επιθήματα στις αντικαταστάσεις γραμματοσειρών για να αποφύγει τις συγκρούσεις μεταξύ των αρχικών γραμματοσειρών και των αντικατασταθέντων γραμματοσειρών. Αυτό βοηθά στη διασφάλιση της μέγιστης συμβατότητας κατά τη μετατροπή και τον χειρισμό εγγράφων.

#### Ε: Πώς μπορώ να ανακτήσω αντικαταστάσεις γραμματοσειρών χωρίς επιθήματα στο Aspose.Words;

 Α: Για να ανακτήσετε αντικαταστάσεις γραμματοσειρών χωρίς επιθήματα στο Aspose.Words, μπορείτε να χρησιμοποιήσετε το`FontSubstitutionSettings` τάξη και το`RemoveSuffixes` ιδιοκτησία. Ρύθμιση αυτής της ιδιότητας σε`true` θα λάβει τις αντικαταστάσεις γραμματοσειράς χωρίς τα πρόσθετα επιθήματα.

#### Ε: Είναι δυνατόν να απενεργοποιήσετε την προσθήκη επιθημάτων σε αντικαταστάσεις γραμματοσειρών στο Aspose.Words;

Α: Όχι, δεν είναι δυνατό να απενεργοποιήσετε την προσθήκη επιθημάτων σε αντικαταστάσεις γραμματοσειρών στο Aspose.Words. Τα επιθήματα προστίθενται από προεπιλογή για να διασφαλιστεί η συμβατότητα και η συνέπεια των εγγράφων.

#### Ε: Πώς μπορώ να φιλτράρω τα ανεπιθύμητα επιθήματα σε αντικαταστάσεις γραμματοσειρών στο Aspose.Words;

 Α: Για να φιλτράρετε τα ανεπιθύμητα επιθήματα σε αντικαταστάσεις γραμματοσειρών στο Aspose.Words, μπορείτε να χρησιμοποιήσετε τεχνικές επεξεργασίας συμβολοσειρών, όπως η χρήση του`Replace` ή`Substring` μεθόδους για την αφαίρεση συγκεκριμένων επιθημάτων που δεν θέλετε να συμπεριλάβετε.