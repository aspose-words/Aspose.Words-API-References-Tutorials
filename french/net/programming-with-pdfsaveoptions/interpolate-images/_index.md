---
title: Interpoler des images
linktitle: Interpoler des images
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour activer l'interpolation d'image avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/interpolate-images/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonction d'interpolation d'image avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment activer l'interpolation d'image lors de la conversion en PDF.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle "Rendering.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF avec interpolation d'image

 Pour activer l'interpolation des images lors de la conversion en PDF, nous devons configurer le`PdfSaveOptions` objet en définissant le`InterpolateImages` propriété à`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };
```

## Étape 4 : Enregistrez le document au format PDF avec interpolation de trame

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

C'est tout ! Vous avez activé avec succès l'interpolation d'image lors de la conversion d'un document au format PDF à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour l'interpolation d'images avec Aspose.Words pour .NET


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);

```
