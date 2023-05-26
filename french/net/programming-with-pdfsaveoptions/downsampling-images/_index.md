---
title: Images de sous-échantillonnage
linktitle: Images de sous-échantillonnage
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à réduire la résolution de l'image lors de la conversion au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/downsampling-images/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes pour réduire la résolution de l'image lors de la conversion au format PDF avec Aspose.Words pour .NET. Cela réduit la taille du fichier PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre document.

## Étape 2 : Configurer les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et définissez les options de réduction d'image :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Le`Resolution` propriété spécifie la résolution cible des images et la`ResolutionThreshold` La propriété spécifie la résolution minimale en dessous de laquelle les images ne seront pas réduites.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options d'enregistrement :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour le sous-échantillonnage d'images à l'aide d'Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//Nous pouvons définir un seuil minimum pour le sous-échantillonnage.
	// Cette valeur empêchera la deuxième image du document d'entrée d'être sous-échantillonnée.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

En suivant ces étapes, vous pouvez facilement réduire la résolution de l'image lors de la conversion au format PDF avec Aspose.Words pour .NET.


