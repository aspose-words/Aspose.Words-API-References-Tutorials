---
title: Πολυτμήμα
linktitle: Πολυτμήμα
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να ανακτάτε και να επεξεργάζεστε ετικέτες δομημένων εγγράφων πολλών τμημάτων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-sdt/multi-section/
---

Αυτό το σεμινάριο εξηγεί πώς να εργαστείτε με ετικέτες δομημένων εγγράφων πολλών ενοτήτων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Μπορείτε να ανακτήσετε και να επεξεργαστείτε τις ετικέτες ενότητας που υπάρχουν στο έγγραφο.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, πρέπει να έχετε τα εξής:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.Words για .NET.
- Βασικές γνώσεις C# και Επεξεργασία λέξεων με έγγραφα Word.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων
 Ξεκινήστε ρυθμίζοντας τη διαδρομή προς τον κατάλογο εγγράφων σας. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφό σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο και ανακτήστε ετικέτες πολλών τμημάτων
 Φορτώστε το έγγραφο του Word χρησιμοποιώντας το`Document` κατασκευαστή, περνώντας τη διαδρομή προς το έγγραφο ως παράμετρο. Ανακτήστε όλους τους κόμβους έναρξης εύρους ετικετών δομημένου εγγράφου στο έγγραφο χρησιμοποιώντας το`GetChildNodes` μέθοδος.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Βήμα 3: Επεξεργαστείτε τις ετικέτες πολλών τμημάτων
Επανάληψη μέσω της συλλογής κόμβων έναρξης εύρους ετικετών δομημένου εγγράφου. Σε αυτό το παράδειγμα, απλώς εκτυπώνουμε τον τίτλο κάθε ετικέτας στην κονσόλα. Μπορείτε να εκτελέσετε περαιτέρω επεξεργασία με βάση τις απαιτήσεις σας.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Παράδειγμα πηγαίου κώδικα για Multi Section χρησιμοποιώντας Aspose.Words για .NET 

```csharp
	// Διαδρομή στον κατάλογο εγγράφων σας
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Αυτό είναι! Έχετε ανακτήσει και επεξεργαστεί επιτυχώς ετικέτες δομημένων εγγράφων πολλών τμημάτων στο έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.