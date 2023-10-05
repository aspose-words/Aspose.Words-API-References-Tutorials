---
title: Résoudre les noms de polices
linktitle: Résoudre les noms de polices
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour résoudre les noms de polices manquants lors de la conversion en HTML avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/resolve-font-names/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour résoudre les noms de polices manquants avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de résoudre automatiquement les noms de polices manquants lors de la conversion d'un document en HTML.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous chargerons le document à traiter. Utilisez le code suivant pour charger le document à partir d'un répertoire spécifié :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Ce code crée une instance de`Document` en chargeant le document à partir du répertoire spécifié.

## Étape 3 : Configuration des options de sauvegarde HTML

Nous allons maintenant configurer les options de sauvegarde HTML pour résoudre les noms de polices manquants lors de la conversion. Utilisez le code suivant :

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Ce code crée une instance de`HtmlSaveOptions`et définit le`ResolveFontNames` possibilité de`true`pour résoudre les noms de polices manquants lors de la conversion en HTML. Également`PrettyFormat` l'option est définie sur`true` pour obtenir un code HTML bien formaté.

## Étape 4 : Conversion et enregistrement du document au format HTML

Enfin, nous convertirons le document en HTML en utilisant les options d'enregistrement HTML configurées précédemment. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Ce code convertit le document en HTML en résolvant automatiquement les noms de polices manquants et enregistre le fichier HTML converti dans le répertoire spécifié.

### Exemple de code source pour résoudre les noms de polices à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Assurez-vous de spécifier le chemin correct vers le répertoire des documents dans le`dataDir` variable.