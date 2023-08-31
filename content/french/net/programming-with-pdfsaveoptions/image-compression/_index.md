---
title: Compression d'image dans un document PDF
linktitle: Compression d'image dans un document PDF
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour compresser des images dans un document PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/image-compression/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonctionnalité de compression d'image dans un document PDF avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment compresser des images dans un document et générer un PDF avec une compression d'image appropriée.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words for .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin d’accès au répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle « Rendering.docx » et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF avec compression d'image

 Pour compresser les images lors de la conversion en PDF, nous devons configurer le`PdfSaveOptions` objet. Nous pouvons définir le type de compression d'image, la qualité JPEG et d'autres options de conformité PDF si nécessaire.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Étape 4 : Enregistrez le document au format PDF avec compression d'image

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options de sauvegarde configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Étape 5 : Configurer les options d'enregistrement au format PDF/A-2u avec compression d'image

Si vous souhaitez générer un PDF compatible PDF/A-2u avec compression d'image, vous pouvez configurer les options d'enregistrement supplémentaires.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Utilisez la compression JPEG avec une qualité de 50 % pour réduire la taille du fichier.
};
```

## Étape 6 : Enregistrez le document au format PDF/A-2u avec compression d'image

Enregistrez le document au format PDF/A-2u à l'aide des options d'enregistrement supplémentaires configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



C'est tout ! Vous avez compressé avec succès les images d'un document et généré un PDF avec une compression d'image appropriée à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour compresser des images avec Aspose.Words for .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Utilisez la compression JPEG avec une qualité de 50 % pour réduire la taille du fichier.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment compresser des images dans un document PDF à l'aide d'Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement réduire la taille des images de votre document PDF et générer un PDF avec une compression d'image appropriée. Utilisez les fonctionnalités de compression d'image d'Aspose.Words for .NET pour optimiser la taille de vos documents PDF tout en préservant la qualité de l'image.

### Questions fréquemment posées

#### Q : Qu'est-ce que la compression d'image dans un document PDF ?
R : La compression d'images dans un document PDF consiste à réduire la taille des images incluses dans le document PDF afin de réduire la taille globale du fichier PDF. Cela réduit l'espace de stockage nécessaire et améliore les performances lors du chargement et de la visualisation du PDF.

#### Q : Comment puis-je compresser des images dans un document PDF avec Aspose.Words pour .NET ?
R : Pour compresser des images dans un document PDF avec Aspose.Words for .NET, suivez ces étapes :

 Créez une instance du`Document` classe spécifiant le chemin d’accès au document Word.

 Créez une instance du`PdfSaveOptions`classe et définir le`ImageCompression` propriété à`PdfImageCompression.Jpeg` pour utiliser la compression JPEG.

Vous pouvez également définir d'autres options de compression d'image, telles que la qualité JPEG, en fonction de vos besoins.

 Utilisez le`Save` méthode du`Document`classe pour enregistrer le document au format PDF en spécifiant les options d'enregistrement.

#### Q : Quelle est la différence entre la compression d’image standard et la compression d’image PDF/A-2u ?
R : La compression d'image standard réduit la taille des images dans un document PDF tout en préservant les champs du formulaire. Cela réduit la taille globale du fichier PDF sans compromettre la fonctionnalité des champs de formulaire.

La compression d'image avec PDF/A-2u est une option supplémentaire qui vous permet de générer un fichier PDF conforme à la norme PDF/A-2u tout en appliquant la compression d'image. PDF/A-2u est une norme ISO pour les documents PDF d'archivage et garantit la conservation à long terme des documents.
