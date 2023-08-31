---
title: Ajouter un préfixe de nom de classe CSS
linktitle: Ajouter un préfixe de nom de classe CSS
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour ajouter un préfixe de nom de classe CSS lors de la conversion d'un document en HTML avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour ajouter un préfixe de nom de classe CSS avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'ajouter un préfixe personnalisé aux noms de classes CSS générés lors de la conversion d'un document en HTML.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous chargerons le document Word que nous souhaitons convertir en HTML. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Définir les options d'enregistrement HTML

Définissons maintenant les options d'enregistrement HTML, y compris le type de feuille de style CSS et le préfixe du nom de classe CSS. Utilisez le code suivant :

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Ce code crée une instance de`HtmlSaveOptions` et des ensembles`CssStyleSheetType` à`CssStyleSheetType.External`pour générer une feuille de style CSS externe, et`CssClassNamePrefix` à`"pfx_"` préfixer`"pfx_"` aux noms de classe CSS.

## Étape 4 : Conversion et enregistrement du document au format HTML

Enfin, nous convertirons le document en HTML en utilisant les options de sauvegarde HTML définies précédemment. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Ce code convertit le document en HTML et l'enregistre dans un fichier avec le préfixe de nom de classe CSS ajouté.

### Exemple de code source pour ajouter un préfixe de nom de classe CSS à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Assurez-vous de spécifier le chemin d'accès correct au document dans le champ`dataDir` variable.

Vous avez maintenant appris comment ajouter un préfixe de nom de classe CSS lors de la conversion d'un document en HTML à l'aide d'Aspose.Words pour .NET. En suivant les étapes du guide étape par étape fournies dans ce didacticiel, vous pouvez personnaliser les noms de classes CSS dans vos documents HTML convertis.