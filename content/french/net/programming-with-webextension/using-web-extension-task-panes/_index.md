---
title: Utilisation des volets de tâches d'extension Web
linktitle: Utilisation des volets de tâches d'extension Web
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour utiliser les volets de tâches d’extension Web avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-webextension/using-web-extension-task-panes/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser les volets de tâches de l'extension Web avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous pourrez comprendre comment ajouter et configurer des volets de tâches pour les extensions Web.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words for .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le document généré. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer et configurer un volet de tâches

 Nous créons un`TaskPane` objet et ajoutez-le au document`s `Collection WebExtensionTaskPanes. Ensuite, nous configurons les propriétés du volet des tâches, telles que son état ancré, sa visibilité et sa largeur.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Nous définissons également les informations d'identification de l'extension Web, notamment l'identifiant du catalogue, la version et le type de magasin.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Enfin, nous ajoutons des propriétés et des liaisons à l'extension Web.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Étape 3 : Enregistrez et chargez le document

Nous enregistrons le document avec les volets de tâches configurés dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Étape 4 : Afficher les informations sur les volets de tâches

Ensuite, nous chargeons le document et affichons les informations sources du volet des tâches.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

C'est tout ! Vous avez utilisé avec succès les volets de tâches de l'extension Web avec Aspose.Words pour .NET.

### Exemple de code source pour l'utilisation des volets de tâches d'extension Web avec Aspose.Words for .NET


```csharp

	// Le chemin d'accès au répertoire des documents.
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
