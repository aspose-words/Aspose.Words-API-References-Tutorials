---
title: Διαβάστε τις ιδιότητες του Active XControl από το αρχείο Word
linktitle: Διαβάστε τις ιδιότητες του Active XControl από το αρχείο Word
second_title: Aspose.Words Document Processing API
description: Διαβάστε τις ιδιότητες των στοιχείων ελέγχου ActiveX σε ένα αρχείο Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας δείξουμε πώς να διαβάζετε τις ιδιότητες των στοιχείων ελέγχου ActiveX σε ένα αρχείο Word χρησιμοποιώντας το Aspose.Words για .NET. Θα σας παρέχουμε τον πλήρη πηγαίο κώδικα και θα σας δείξουμε πώς να μορφοποιήσετε την έξοδο σήμανσης.

## Βήμα 1: Αρχικοποίηση εγγράφου

 Το πρώτο βήμα είναι να αρχικοποιήσετε το`Document` αντικείμενο φορτώνοντας το έγγραφο του Word που περιέχει τα στοιχεία ελέγχου ActiveX. Φροντίστε να αντικαταστήσετε`MyDir` με την πραγματική διαδρομή προς τον κατάλογο που περιέχει το έγγραφο.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Βήμα 2: Ανάκτηση στοιχείων ελέγχου ActiveX

 Σε αυτό το βήμα, θα επαναλάβουμε το καθένα`Shape` του εγγράφου για να ανακτήσετε τα στοιχεία ελέγχου ActiveX και να διαβάσετε τις ιδιότητές τους.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Παράδειγμα πηγαίου κώδικα για τις ιδιότητες Read Active XControl χρησιμοποιώντας Aspose.Words για .NET

Ακολουθεί ο πλήρης πηγαίος κώδικας για την ανάγνωση ιδιοτήτων των στοιχείων ελέγχου ActiveX χρησιμοποιώντας το Aspose.Words για .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## συμπέρασμα

Αυτός ο οδηγός σάς έδειξε πώς να διαβάζετε τις ιδιότητες των στοιχείων ελέγχου ActiveX σε ένα αρχείο Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τα βήματα που περιγράφονται, μπορείτε να αρχικοποιήσετε το έγγραφο, να ανακτήσετε στοιχεία ελέγχου ActiveX και να διαβάσετε τις ιδιότητές τους. Χρησιμοποιήστε το δείγμα κώδικα που παρέχεται ως σημείο εκκίνησης και προσαρμόστε τον στις συγκεκριμένες ανάγκες σας.

Η ανάγνωση των ιδιοτήτων των στοιχείων ελέγχου ActiveX σάς επιτρέπει να εξαγάγετε σημαντικές πληροφορίες από τα αρχεία του Word που περιέχουν αυτά τα στοιχεία ελέγχου. Το Aspose.Words για .NET προσφέρει ισχυρές δυνατότητες για επεξεργασία λέξεων με στοιχεία ελέγχου ActiveX και αυτοματοποίηση της επεξεργασίας των εγγράφων σας.

### Συχνές ερωτήσεις

#### Ε: Ποιο είναι το πρώτο βήμα για την ανάγνωση ιδιοτήτων των στοιχείων ελέγχου ActiveX σε ένα αρχείο Word;

 Α: Το πρώτο βήμα είναι να αρχικοποιήσετε το`Document` αντικείμενο φορτώνοντας το έγγραφο του Word που περιέχει τα στοιχεία ελέγχου ActiveX. Φροντίστε να αντικαταστήσετε`MyDir` με την πραγματική διαδρομή προς τον κατάλογο που περιέχει το έγγραφο.

#### Ε: Πώς μπορώ να εισάγω στοιχεία ελέγχου ActiveX στο έγγραφο;

 Α: Για να ανακτήσετε στοιχεία ελέγχου ActiveX, πρέπει να επαναλάβετε το καθένα`Shape` του εγγράφου και ελέγξτε αν πρόκειται για στοιχείο ελέγχου ActiveX. Χρησιμοποιήστε το`OleFormat` Ιδιοκτησία του`Shape` για πρόσβαση στο`OleControl` αντικείμενο και να ανακτήσετε τις απαραίτητες ιδιότητες.

#### Ε: Ποιες ιδιότητες των στοιχείων ελέγχου ActiveX μπορώ να διαβάσω;

Α: Μπορείτε να διαβάσετε διάφορες ιδιότητες των στοιχείων ελέγχου ActiveX, όπως λεζάντα, τιμή, κατάσταση ενεργοποίησης ή απενεργοποίησης, τύπος και childNodes που σχετίζονται με το στοιχείο ελέγχου.

#### Ε: Πώς μπορώ να βρω τον συνολικό αριθμό των στοιχείων ελέγχου ActiveX στο έγγραφο;

 Α: Για να λάβετε τον συνολικό αριθμό των στοιχείων ελέγχου ActiveX στο έγγραφο, μπορείτε να χρησιμοποιήσετε το`GetChildNodes` μέθοδος του`Document` αντικείμενο που προσδιορίζει το`NodeType.Shape` τύπου και συμπεριλαμβανομένων των θυγατρικών κόμβων.