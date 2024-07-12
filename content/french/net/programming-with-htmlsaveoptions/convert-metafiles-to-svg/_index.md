---
title: Convertir des métafichiers en SVG
linktitle: Convertir des métafichiers en SVG
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour convertir des métafichiers au format SVG lors de la conversion d'un document au format HTML avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour convertir les métafichiers au format SVG avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de convertir des métafichiers au format SVG lors de la conversion d'un document en HTML.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Insérer une image SVG dans le document

Dans cette étape, nous allons insérer une image SVG dans le document à convertir. Utilisez le code suivant pour insérer une image SVG à l'aide d'une balise HTML :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Ce code crée une instance de`Document`et`DocumentBuilder` pour construire le document. Il insère un`<svg>` balise contenant un`<polygon>` élément avec des attributs pour définir la forme et le style de l’image SVG.

## Étape 3 : Définir les options d'enregistrement HTML

Nous allons maintenant définir les options de sauvegarde HTML, en spécifiant que les métafichiers doivent être convertis au format SVG. Utilisez le code suivant :

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Ce code crée une instance de`HtmlSaveOptions` et des ensembles`MetafileFormat` à`HtmlMetafileFormat.Svg` pour spécifier que les métafichiers doivent être convertis au format SVG lors de la conversion en HTML.

## Étape 4 : Conversion et enregistrement du document au format HTML

Enfin, nous convertirons le document en HTML en utilisant les options de sauvegarde HTML définies précédemment. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Ce code convertit le document en HTML et l'enregistre dans un fichier avec les métafichiers convertis en SVG.

### Exemple de code source pour convertir des métafichiers en SVG à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
