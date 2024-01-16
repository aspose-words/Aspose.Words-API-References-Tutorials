---
title: Χρήση παραθύρων εργασιών επέκτασης Web
linktitle: Χρήση παραθύρων εργασιών επέκτασης Web
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη χρήση των παραθύρων εργασιών επέκτασης Web με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-webextension/using-web-extension-task-panes/
---

Αυτό το άρθρο παρέχει έναν οδηγό βήμα προς βήμα σχετικά με τον τρόπο χρήσης των παραθύρων εργασιών επέκτασης ιστού με το Aspose.Words για .NET. Θα εξηγήσουμε λεπτομερώς κάθε μέρος του κώδικα. Στο τέλος αυτού του σεμιναρίου, θα μπορείτε να κατανοήσετε πώς να προσθέτετε και να διαμορφώνετε τα παράθυρα εργασιών για επεκτάσεις ιστού.

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει τη βιβλιοθήκη Aspose.Words για .NET στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη και τις οδηγίες εγκατάστασης στον ιστότοπο Aspose.

## Βήμα 1: Ορίστε τον κατάλογο εγγράφων

 Για να ξεκινήσετε, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το έγγραφο που δημιουργήθηκε. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε και διαμορφώστε ένα παράθυρο εργασιών

 Δημιουργούμε α`TaskPane` αντικείμενο και προσθέστε το στο έγγραφο`s `Συλλογή WebExtensionTaskPanes. Στη συνέχεια, διαμορφώνουμε τις ιδιότητες του παραθύρου εργασιών, όπως την κατάσταση σύνδεσης, την ορατότητα και το πλάτος του.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Επίσης, ορίσαμε τα διαπιστευτήρια της επέκτασης ιστού, συμπεριλαμβανομένου του αναγνωριστικού καταλόγου, της έκδοσης και του τύπου καταστήματος.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Τέλος, προσθέτουμε ιδιότητες και δεσμεύσεις στην επέκταση ιστού.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Βήμα 3: Αποθηκεύστε και φορτώστε το έγγραφο

Αποθηκεύουμε το έγγραφο με τα παράθυρα εργασιών που έχουν ρυθμιστεί στον καθορισμένο κατάλογο.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Βήμα 4: Εμφάνιση των πληροφοριών των παραθύρων εργασιών

Στη συνέχεια, φορτώνουμε το έγγραφο και εμφανίζουμε τις πληροφορίες πηγής του παραθύρου εργασιών.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

Αυτό είναι όλο ! Χρησιμοποιήσατε με επιτυχία τα παράθυρα εργασιών επέκτασης ιστού με το Aspose.Words για .NET.

### Παράδειγμα πηγαίου κώδικα για τη χρήση πλαισίων εργασιών επέκτασης ιστού με το Aspose.Words για .NET


```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	TaskPane taskPane = new TaskPane();
	doc.WebExtensionTaskPanes.Add(taskPane);

	taskPane.DockState = TaskPaneDockState.Right;
	taskPane.IsVisible = true;
	taskPane.Width = 300;

	taskPane.WebExtension.Reference.Id = "wa102923726";
	taskPane.WebExtension.Reference.Version = "1.0.0.0";
	taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
	taskPane.WebExtension.Reference.Store = "th-TH";
	taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
	taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
		WebExtensionBindingType.Text, "194740422"));

	doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	
	
	doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	Console.WriteLine("Task panes sources:\n");

	foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
	{
		WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
		Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
	}
 
```
