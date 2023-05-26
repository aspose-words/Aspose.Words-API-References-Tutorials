---
title: Convertir les métafichiers en Emf ou Wmf
linktitle: Convertir les métafichiers en Emf ou Wmf
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour convertir des métafichiers aux formats EMF ou WMF lors de la conversion d'un document au format HTML avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour convertir des métafichiers au format EMF ou WMF avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de convertir des images au format métafichier vers des formats plus compatibles tels que EMF ou WMF lors de la conversion d'un document au format HTML.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Insertion d'une image dans le document

Dans cette étape, nous allons insérer une image dans le document à convertir. Utilisez le code suivant pour insérer une image à partir d'une source de données à l'aide d'une balise HTML :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Ce code crée une instance de`Document` et`DocumentBuilder` pour construire le document. Il insère un`<img>` tag dans le document avec une image encodée en base64.

## Étape 3 : Définir les options d'enregistrement HTML

Nous allons maintenant définir les options d'enregistrement HTML, y compris le format de métafichier à utiliser pour les images. Utilisez le code suivant :

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Ce code crée une instance de`HtmlSaveOptions` et ensembles`MetafileFormat` pour`HtmlMetafileFormat.EmfOrWmf` pour spécifier que les métafichiers doivent être convertis au format EMF ou WMF lors de la conversion au format HTML.

## Étape 4 : Conversion et enregistrement du document au format HTML

Enfin nous allons convertir le document en HTML en utilisant les options d'enregistrement HTML précédemment définies. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Ce code convertit le document au format HTML et l'enregistre dans un fichier avec les métafichiers convertis au format EMF ou WMF selon les options d'enregistrement définies.

### Exemple de code source pour convertir des métafichiers en Emf ou Wmf à l'aide de Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Assurez-vous de spécifier le chemin d'accès correct au répertoire de documents dans le`dataDir` variable.

Vous avez maintenant appris à convertir des métafichiers aux formats EMF ou WMF lors de la conversion d'un document au format HTML à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement gérer les métafichiers dans vos documents HTML convertis.