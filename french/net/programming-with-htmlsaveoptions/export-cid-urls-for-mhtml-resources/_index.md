---
title: Exporter les URL Cid pour les ressources Mhtml
linktitle: Exporter les URL Cid pour les ressources Mhtml
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour exporter les URL CID des ressources MHTML lors de l'enregistrement d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C # pour exporter des URL CID pour les ressources MHTML avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'exporter les URL CID des ressources MHTML lors de l'enregistrement d'un document au format MHTML.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document à exporter. Utilisez le code suivant pour charger le document à partir d'un répertoire spécifié :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Ce code crée une instance de`Document` en chargeant le document depuis le répertoire spécifié.

## Étape 3 : Configuration des options de sauvegarde HTML

Nous allons maintenant configurer les options d'enregistrement HTML pour exporter les URL CID des ressources MHTML. Utilisez le code suivant :

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Ce code crée une instance de`HtmlSaveOptions` avec le format d'enregistrement défini sur MHTML. Il permet également l'exportation des URL CID des ressources MHTML en définissant`ExportCidUrlsForMhtmlResources` pour`true`.

## Étape 4 : conversion et enregistrement du document au format MHTML

Enfin, nous convertirons le document en MHTML en utilisant les options d'enregistrement HTML configurées précédemment. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Ce code convertit le document en MHTML et l'enregistre dans un fichier avec les URL CID des ressources MHTML exportées.

### Exemple de code source pour Exporter les URL Cid pour les ressources Mhtml à l'aide de Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Assurez-vous de spécifier le chemin d'accès correct au répertoire de documents dans le`dataDir` variable.

Vous avez maintenant appris à exporter les URL CID des ressources MHTML lors de l'enregistrement d'un document au format MHTML à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement gérer les URL CID dans vos documents MHTML exportés.

