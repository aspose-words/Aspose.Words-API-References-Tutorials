---
title: Exporter les informations aller-retour
linktitle: Exporter les informations aller-retour
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour exporter des informations aller-retour lors de l'enregistrement d'un document au format HTML avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour exporter les informations aller-retour à partir d'un document avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'inclure des informations aller-retour dans le fichier HTML exporté, ce qui facilite la récupération des modifications apportées au document d'origine.

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

Nous allons maintenant configurer les options de sauvegarde HTML pour exporter les informations aller-retour du document. Utilisez le code suivant :

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Ce code crée une instance de`HtmlSaveOptions` et définit le`ExportRoundtripInformation` possibilité de`true` pour inclure des informations aller-retour lors de l’exportation.

## Étape 4 : Conversion et enregistrement du document au format HTML

Enfin, nous convertirons le document en HTML en utilisant les options d'enregistrement HTML configurées précédemment. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Ce code convertit le document en HTML, y compris les informations aller-retour, et enregistre le fichier HTML exporté dans le répertoire spécifié.

### Exemple de code source pour exporter des informations aller-retour à l'aide d'Aspose.Words pour .NET


```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Assurez-vous de spécifier le chemin correct vers le répertoire des documents dans le`dataDir` variable.