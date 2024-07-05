---
title: Ajouter un filigrane de texte avec des options spécifiques
linktitle: Ajouter un filigrane de texte avec des options spécifiques
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter un filigrane de texte avec des options spécifiques à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

Dans ce didacticiel, nous vous expliquerons comment ajouter un filigrane de texte avec des options spécifiques à l'aide d'Aspose.Words pour .NET. Un filigrane de texte est un texte superposé sur un document pour indiquer qu'il s'agit d'un brouillon, confidentiel, etc.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargement du document

Nous allons charger un document existant en utilisant le chemin du document.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Étape 3 : Ajouter un filigrane de texte avec des options spécifiques

 Nous allons créer une instance du`TextWatermarkOptions`classe et définissez les options souhaitées pour le filigrane de texte.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Étape 4 : Enregistrez le document

Enfin, nous pouvons enregistrer le document avec le filigrane de texte ajouté.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Exemple de code source pour ajouter un filigrane de texte avec des options spécifiques avec Aspose.Words for .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Félicitation ! Vous avez maintenant appris à ajouter un filigrane de texte avec des options spécifiques à l'aide d'Aspose.Words pour .NET.

