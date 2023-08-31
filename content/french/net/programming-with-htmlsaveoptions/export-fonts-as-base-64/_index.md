---
title: Exporter les polices en base 64
linktitle: Exporter les polices en base 64
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour exporter les polices base 64 lors de l’enregistrement d’un document avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour exporter des polices base 64 avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'exporter des polices sous forme de données base 64 lors de l'enregistrement d'un document au format HTML.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document à exporter. Utilisez le code suivant pour charger le document à partir d'un répertoire spécifié :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ce code crée une instance de`Document` en chargeant le document à partir du répertoire spécifié.

## Étape 3 : Configuration des options de sauvegarde HTML

Nous allons maintenant configurer les options de sauvegarde HTML pour exporter les polices base 64. Utilisez le code suivant :

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Ce code crée une instance de`HtmlSaveOptions` et des ensembles`ExportFontsAsBase64` à`true` pour spécifier que les polices doivent être exportées en tant que données base 64 lors de l'enregistrement au format HTML.

## Étape 4 : Conversion et enregistrement du document au format HTML

Enfin, nous convertirons le document en HTML en utilisant les options d'enregistrement HTML configurées précédemment. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Ce code convertit le document en HTML et l'enregistre dans un fichier avec les polices exportées sous forme de données base 64.

### Exemple de code source pour exporter les polices en base 64 à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Assurez-vous de spécifier le chemin correct vers le répertoire des documents dans le`dataDir` variable.

Vous avez maintenant appris à exporter des polices base 64 lors de l'enregistrement d'un document au format HTML à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement exporter des polices de manière sécurisée et les intégrer dans vos documents HTML.