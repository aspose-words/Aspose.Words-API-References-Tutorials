---
title: Mettre à l'échelle les polices WMF à la taille du métafichier
linktitle: Mettre à l'échelle les polices WMF à la taille du métafichier
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour ajuster la taille de la police WMF lors de la conversion en PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Cet article fournit un guide étape par étape sur l'utilisation de la fonction de mise à l'échelle des polices WMF à la taille du métafichier avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment activer ou désactiver la mise à l'échelle des polices WMF lors de la conversion en PDF.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle "WMF avec text.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Étape 3 : Configurer les options de rendu des métafichiers

 Pour activer ou désactiver la mise à l'échelle des polices WMF à la taille du métafichier, nous devons configurer le`MetafileRenderingOptions` objet. Dans cet exemple, nous désactivons la mise à l'échelle des polices en définissant le paramètre`ScaleWmfFontsToMetafileSize` propriété à`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Étape 4 : Configurez les options d'enregistrement au format PDF avec les options de rendu des métafichiers

Enfin, nous pouvons configurer les options d'enregistrement au format PDF à l'aide des options de rendu de métafichier configurées précédemment.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Étape 5 : Enregistrer le document au format PDF avec les options de rendu des métafichiers

Enregistrez le document au format PDF en utilisant les options d'enregistrement précédemment configurées.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

C'est tout ! Vous avez activé ou désactivé avec succès la mise à l'échelle des polices WMF à la taille du métafichier lors de la conversion

un document PDF en utilisant Aspose.Words pour .NET.

### Exemple de code source pour la mise à l'échelle des polices WMF à la taille du métafichier avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Si Aspose.Words ne peut pas restituer correctement certains des enregistrements de métafichier en graphiques vectoriels
	// puis Aspose.Words restitue ce métafichier en bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```
