---
title: Exporter des ressources
linktitle: Exporter des ressources
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour exporter des ressources de document lors de l'enregistrement au format HTML avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/export-resources/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C # pour exporter des ressources de document avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'exporter des ressources, telles que des polices, en tant que fichiers externes lors de l'enregistrement d'un document au format HTML.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document à exporter. Utilisez le code suivant pour charger le document à partir d'un répertoire spécifié :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ce code crée une instance de`Document` en chargeant le document depuis le répertoire spécifié.

## Étape 3 : Configuration des options de sauvegarde HTML

Nous allons maintenant configurer les options d'enregistrement HTML pour exporter les ressources du document. Utilisez le code suivant :

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://exemple.com/ressources"
};
```

 Ce code crée une instance de`HtmlSaveOptions` et définit les options suivantes :

- `CssStyleSheetType` est réglé sur`CssStyleSheetType.External`pour exporter la feuille de style CSS vers un fichier externe.
- `ExportFontResources` est réglé sur`true` pour exporter les ressources de police.
- `ResourceFolder` spécifie le répertoire de destination où les ressources seront enregistrées.
- `ResourceFolderAlias` spécifie l'alias d'URL qui sera utilisé pour accéder aux ressources.

## Étape 4 : Conversion et enregistrement du document au format HTML

Enfin, nous convertirons le document en HTML en utilisant les options d'enregistrement HTML configurées précédemment. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Ce code convertit le document en HTML et enregistre les ressources dans le répertoire spécifié, en utilisant l'alias d'URL spécifié.

### Exemple de code source pour les ressources d'exportation à l'aide d'Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://exemple.com/ressources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Assurez-vous de spécifier le chemin d'accès correct au répertoire de documents dans le`dataDir` variable.