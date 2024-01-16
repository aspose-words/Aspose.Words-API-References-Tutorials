---
title: Taakvensters voor webextensies gebruiken
linktitle: Taakvensters voor webextensies gebruiken
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het gebruik van taakvensters voor webextensies met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-webextension/using-web-extension-task-panes/
---

Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de taakvensters van de webextensies met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u taakvensters voor webextensies toevoegt en configureert.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer de documentmap

 Om te beginnen moet u het pad definiëren naar de map waar u het gegenereerde document wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak en configureer een taakvenster

 Wij creëren een`TaskPane` object en voeg het toe aan het document`s `WebExtensionTaskPanes-collectie. Vervolgens configureren we de eigenschappen van het taakvenster, zoals de vastgezette status, zichtbaarheid en breedte.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

We stellen ook de inloggegevens voor de webextensie in, inclusief catalogus-ID, versie en winkeltype.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Ten slotte voegen we eigenschappen en bindingen toe aan de webextensie.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Stap 3: Bewaar en laad het document

We slaan het document op met de taakvensters geconfigureerd in de opgegeven map.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Stap 4: Geef de informatie over de taakvensters weer

Vervolgens laden we het document en geven we de broninformatie van het taakvenster weer.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

Dat is alles ! U hebt de taakvensters van de webextensie met succes gebruikt met Aspose.Words voor .NET.

### Voorbeeldbroncode voor het gebruik van taakvensters van webextensies met Aspose.Words voor .NET


```csharp

	// Het pad naar de documentenmap.
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
