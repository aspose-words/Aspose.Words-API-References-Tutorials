---
title: Appliquer les bordures et l'ombrage au paragraphe
linktitle: Appliquer les bordures et l'ombrage au paragraphe
second_title: API de traitement de documents Aspose.Words
description: Apprenez à appliquer des bordures et des ombres à un paragraphe avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

Dans ce didacticiel, nous allons vous montrer comment appliquer des bordures et un ombrage à un paragraphe à l'aide des fonctionnalités d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications de mise en forme.

## Étape 1 : Création et configuration du document

Pour commencer, créez un nouveau document et un objet DocumentBuilder associé. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : configuration des bordures

Configurons maintenant les bordures de paragraphe en spécifiant le style de bordure pour chaque côté. Voici comment:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Étape 3 : Configuration du remplissage

Nous allons maintenant configurer le remplissage du paragraphe en spécifiant la texture et les couleurs de remplissage. Voici comment:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Étape 4 : Ajouter du contenu

Nous allons ajouter du contenu formaté au paragraphe. Voici comment:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Exemple de code source pour Appliquer les bordures et l'ombrage au paragraphe à l'aide de Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Appliquer les bordures et l'ombrage au paragraphe avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```
