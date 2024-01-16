---
title: Καταργήστε τον πίνακα περιεχομένων στο έγγραφο του Word
linktitle: Καταργήστε τον πίνακα περιεχομένων στο έγγραφο του Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να αφαιρέσετε τον πίνακα περιεχομένων σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/remove-content/remove-table-of-contents/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον τρόπο κατάργησης του πίνακα περιεχομένων σε ένα έγγραφο του Word χρησιμοποιώντας τη βιβλιοθήκη Aspose.Words για .NET. Ο πίνακας περιεχομένων μπορεί μερικές φορές να είναι περιττός ή περιττός και αυτός ο κωδικός θα σας βοηθήσει να τον αφαιρέσετε αποτελεσματικά. Θα παρέχουμε έναν οδηγό βήμα προς βήμα για να σας βοηθήσουμε να κατανοήσετε και να εφαρμόσετε τον κώδικα στο δικό σας έργο .NET.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα στοιχεία:
- Γνώση εργασίας της γλώσσας προγραμματισμού C#
- Η βιβλιοθήκη Aspose.Words για .NET είναι εγκατεστημένη στο έργο σας
- Ένα έγγραφο του Word που περιέχει έναν πίνακα περιεχομένων που θέλετε να διαγράψετε

## Βήμα 1: Ορίστε τον κατάλογο εγγράφων
 Αρχικά, πρέπει να ορίσετε τη διαδρομή καταλόγου στη θέση του εγγράφου του Word. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στον κωδικό με την κατάλληλη διαδρομή.

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Ανεβάστε το έγγραφο
 Στη συνέχεια, θα φορτώσουμε το έγγραφο του Word σε μια παρουσία του`Document` τάξη χρησιμοποιώντας το`Load` μέθοδος.

```csharp
// Φορτώστε το έγγραφο
Document doc = new Document(dataDir + "your-document.docx");
```

## Βήμα 3: Διαγράψτε τον πίνακα περιεχομένων
 Για να αφαιρέσουμε τον πίνακα περιεχομένων, θα κάνουμε βρόχο μέσω του τύπου TOC (πίνακας περιεχομένων).`FieldStart` κόμβους στο έγγραφο. Θα αποθηκεύσουμε αυτούς τους κόμβους ώστε να έχουμε γρήγορη πρόσβαση σε αυτούς και να δημιουργήσουμε μια λίστα με κόμβους προς διαγραφή.

```csharp
// Αποθηκεύστε τους κόμβους FieldStart των πεδίων TOC στο έγγραφο για γρήγορη πρόσβαση.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Αυτή είναι μια λίστα για την αποθήκευση των κόμβων που βρίσκονται μέσα στο καθορισμένο TOC. Θα διαγραφούν στο τέλος αυτής της μεθόδου.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Ελέγξτε εάν υπάρχει ο καθορισμένος δείκτης TOC.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Είναι ασφαλέστερο να αποθηκεύσετε αυτούς τους κόμβους και να τους διαγράψετε όλους στο τέλος.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Όταν συναντάμε έναν κόμβο FieldEnd τύπου FieldTOC,
     //Ξέρουμε ότι βρισκόμαστε στο τέλος του τρέχοντος TOC και σταματάμε εδώ.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Δείγμα πηγαίου κώδικα για Κατάργηση Πίνακα Περιεχομένων με χρήση του Aspose.Words για .NET 
```csharp

// Διαδρομή στον κατάλογο εγγράφων σας
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Φορτώστε το έγγραφο
Document doc = new Document(dataDir + "your-document.docx");

// Αποθηκεύστε τους κόμβους FieldStart των πεδίων TOC στο έγγραφο για γρήγορη πρόσβαση.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Αυτή είναι μια λίστα για την αποθήκευση των κόμβων που βρίσκονται μέσα στο καθορισμένο TOC. Θα αφαιρεθούν στο τέλος αυτής της μεθόδου.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Βεβαιωθείτε ότι το TOC που καθορίζεται από το ευρετήριο που πέρασε υπάρχει.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Είναι ασφαλέστερο να αποθηκεύσετε αυτούς τους κόμβους και να τους διαγράψετε όλους αμέσως αργότερα.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Μόλις συναντήσουμε έναν κόμβο FieldEnd τύπου FieldTOC,
	// Ξέρουμε ότι βρισκόμαστε στο τέλος του τρέχοντος TOC και σταματάμε εδώ.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## συμπέρασμα
Σε αυτό το σεμινάριο, παρουσιάσαμε έναν οδηγό βήμα προς βήμα για την κατάργηση του πίνακα περιεχομένων από ένα έγγραφο του Word χρησιμοποιώντας τη βιβλιοθήκη Aspose.Words για .NET. Ακολουθώντας τον παρεχόμενο κώδικα και τις οδηγίες, μπορείτε εύκολα να εξαλείψετε τον πίνακα περιεχομένων και να βελτιώσετε τη διάταξη του εγγράφου σας. Θυμηθείτε να προσαρμόσετε τη διαδρομή καταλόγου και τα ονόματα αρχείων ώστε να ταιριάζουν στις συγκεκριμένες ανάγκες σας.

### Συχνές ερωτήσεις

#### Ε: Γιατί πρέπει να χρησιμοποιήσω το Aspose.Words για να αφαιρέσω τον πίνακα περιεχομένων σε ένα έγγραφο του Word;

Α: Το Aspose.Words είναι μια ισχυρή και ευέλικτη βιβλιοθήκη κλάσεων για χειρισμό εγγράφων του Word σε εφαρμογές .NET. Χρησιμοποιώντας το Aspose.Words, μπορείτε να αφαιρέσετε αποτελεσματικά τον πίνακα περιεχομένων από τα έγγραφά σας, κάτι που μπορεί να είναι χρήσιμο εάν ο πίνακας περιεχομένων είναι περιττός ή περιττός. Αυτό σας επιτρέπει να προσαρμόσετε το περιεχόμενο του εγγράφου σας και να βελτιώσετε τη συνολική του παρουσίαση.

#### Ε: Πώς μπορώ να ανεβάσω ένα έγγραφο στο Aspose.Words για .NET;

Α: Για να καταργήσετε τον πίνακα περιεχομένων σε ένα έγγραφο του Word, πρέπει πρώτα να φορτώσετε το έγγραφο στη μνήμη χρησιμοποιώντας τη μέθοδο Load() του Aspose.Words. Ακολουθεί δείγμα κώδικα για τη φόρτωση ενός εγγράφου από έναν συγκεκριμένο κατάλογο:

```csharp
// Διαδρομή στον κατάλογο των εγγράφων σας
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Φορτώστε το έγγραφο
Document doc = new Document(dataDir + "your-document.docx");
```

 Αντικαθιστώ`"YOUR DOCUMENTS DIRECTORY"` με την πραγματική διαδρομή προς το έγγραφό σας.

#### Ε: Πώς μπορώ να αφαιρέσω τον πίνακα περιεχομένων σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words;

 Α: Για να αφαιρέσετε το TOC, πρέπει να επαναλάβετε το`FieldStart` πληκτρολογήστε κόμβους του TOC στο έγγραφο. Μπορείτε να αποθηκεύσετε αυτούς τους κόμβους για γρήγορη πρόσβαση και να δημιουργήσετε μια λίστα με κόμβους προς διαγραφή. Εδώ είναι ένα δείγμα κώδικα:

```csharp
// Αποθηκεύστε τους κόμβους FieldStart των πεδίων TOC στο έγγραφο για γρήγορη πρόσβαση.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Αυτή είναι μια λίστα για την αποθήκευση κόμβων που βρίσκονται μέσα στο καθορισμένο TOC. Θα διαγραφούν στο τέλος αυτής της μεθόδου.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Ελέγξτε εάν υπάρχει το καθορισμένο ευρετήριο του πίνακα περιεχομένων.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Είναι ασφαλέστερο να αποθηκεύσετε αυτούς τους κόμβους και να τους διαγράψετε όλους στο τέλος.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Όταν συναντάμε έναν κόμβο FieldEnd τύπου FieldTOC,
//Ξέρουμε ότι βρισκόμαστε στο τέλος του τρέχοντος TOC και σταματάμε εδώ.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### Ε: Πώς να αποθηκεύσετε το επεξεργασμένο έγγραφο στο Aspose.Words για .NET;

Α: Αφού διαγράψετε τον πίνακα περιεχομένων, πρέπει να αποθηκεύσετε το τροποποιημένο έγγραφο χρησιμοποιώντας τη μέθοδο Save(). Καθορίστε την επιθυμητή διαδρομή και τη μορφή αρχείου εξόδου (π.χ. DOCX) για το επεξεργασμένο έγγραφο. Εδώ είναι ένα δείγμα κώδικα:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```