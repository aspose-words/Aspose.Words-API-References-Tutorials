---
title: Compression d'image dans un document PDF
linktitle: Compression d'image dans un document PDF
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour compresser des images dans un document PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/image-compression/
---

Cet article fournit un guide étape par étape sur l'utilisation de la compression d'image dans une fonctionnalité de document PDF avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment compresser des images dans un document et générer un PDF avec une compression d'image appropriée.

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

## Étape 3 : Configurer les options d'enregistrement au format PDF avec compression d'image

 Pour compresser les images lors de la conversion en PDF, nous devons configurer le`PdfSaveOptions` objet. Nous pouvons définir le type de compression d'image, la qualité JPEG et d'autres options de conformité PDF si nécessaire.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Étape 4 : Enregistrer le document au format PDF avec compression d'image

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Étape 5 : Configurez les options d'enregistrement au format PDF/A-2u avec compression d'image

Si vous souhaitez générer un PDF conforme PDF/A-2u avec compression d'image, vous pouvez configurer les options d'enregistrement supplémentaires.

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



C'est tout ! Vous avez réussi à compresser les images d'un document et à générer un PDF avec une compression d'image appropriée à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour compresser des images avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
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
		JpegQuality = 100, // Utilisez la compression JPEG à 50 % de qualité pour réduire la taille du fichier.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment compresser des images dans un document PDF à l'aide de Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement réduire la taille des images dans votre document PDF et générer un PDF avec une compression d'image appropriée. Utilisez les fonctionnalités de compression d'image d'Aspose.Words pour .NET pour optimiser la taille de vos documents PDF tout en préservant la qualité de l'image.

### Questions fréquemment posées

#### Q : Qu'est-ce que la compression d'image dans un document PDF ?
: La compression d'images dans un document PDF consiste à réduire la taille des images incluses dans le document PDF afin de réduire la taille globale du fichier PDF. Cela réduit l'espace de stockage nécessaire et améliore les performances lors du chargement et de l'affichage du PDF.

#### Q : Comment puis-je compresser des images dans un document PDF avec Aspose.Words pour .NET ?
R : Pour compresser des images dans un document PDF avec Aspose.Words pour .NET, suivez ces étapes :

 Créer une instance de`Document` classe spécifiant le chemin d'accès au document Word.

 Créer une instance de`PdfSaveOptions` classe et définissez la`ImageCompression` propriété à`PdfImageCompression.Jpeg` pour utiliser la compression JPEG.

Vous pouvez également définir d'autres options de compression d'image, telles que la qualité JPEG, en fonction de vos besoins.

 Utilisez le`Save` méthode de la`Document`classe pour enregistrer le document au format PDF en spécifiant les options d'enregistrement.

#### Q : Quelle est la différence entre la compression d'image standard et la compression d'image PDF/A-2u ?
R : La compression d'image standard réduit la taille des images dans un document PDF tout en préservant les champs de formulaire. Cela réduit la taille globale du fichier PDF sans compromettre la fonctionnalité du champ de formulaire.

La compression d'image avec PDF/A-2u est une option supplémentaire qui vous permet de générer un fichier PDF conforme à la norme PDF/A-2u tout en appliquant la compression d'image. PDF/A-2u est une norme ISO pour les documents PDF d'archivage et garantit la conservation à long terme des documents.
