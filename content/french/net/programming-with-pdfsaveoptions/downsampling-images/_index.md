---
title: Réduisez la taille du document PDF grâce au sous-échantillonnage des images
linktitle: Réduisez la taille du document PDF grâce au sous-échantillonnage des images
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment réduire la taille d'un document PDF en sous-échantillonnant les images lors de la conversion en PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/downsampling-images/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes permettant de réduire la taille d'un document PDF en sous-échantillonnant les images lors de la conversion en PDF avec Aspose.Words for .NET. Cela réduit la taille du fichier PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin correct vers votre document.

## Étape 2 : Configurer les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et définissez les options de réduction d'image :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Le`Resolution` La propriété spécifie la résolution cible des images et la`ResolutionThreshold`La propriété spécifie la résolution minimale en dessous de laquelle les images ne seront pas réduites.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options d'enregistrement :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin correct pour enregistrer le PDF converti.

### Exemple de code source pour le sous-échantillonnage d'images à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Nous pouvons définir un seuil minimum de sous-échantillonnage.
	// Cette valeur empêchera le sous-échantillonnage de la deuxième image du document d’entrée.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

En suivant ces étapes, vous pouvez facilement réduire la résolution de l'image lors de la conversion en PDF avec Aspose.Words pour .NET.

## Conclusion

Dans ce didacticiel, nous avons expliqué comment réduire la taille d'un document PDF avec un échantillonnage d'images lors de la conversion en PDF à l'aide d'Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement réduire la résolution des images et la taille du fichier PDF généré. Assurez-vous de spécifier le chemin d'accès correct à votre document et de configurer les options d'échantillonnage d'image selon vos besoins. La réduction de la taille du fichier PDF facilite le partage, le stockage et le chargement rapide du fichier sur différentes plates-formes. Profitez des avantages de la réduction de la taille des documents PDF grâce à l'échantillonnage d'images à l'aide d'Aspose.Words for .NET.

### Questions fréquemment posées

#### Q : Qu'est-ce qui réduit la taille du document PDF avec l'échantillonnage d'images ?
R : Réduire la taille d'un document PDF avec l'échantillonnage d'images consiste à diminuer la taille du fichier PDF généré en réduisant la résolution des images lors de la conversion en PDF. Cela optimise l'utilisation de l'espace de stockage et facilite le partage et le transfert du fichier PDF.

#### Q : Comment puis-je réduire la taille d'un document PDF grâce à l'échantillonnage d'images à l'aide d'Aspose.Words pour .NET ?
R : Pour réduire la taille du document PDF avec l'échantillonnage d'images à l'aide d'Aspose.Words for .NET, procédez comme suit :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document que vous souhaitez convertir en PDF à l'aide du`Document` classe et spécifiez le chemin d'accès au document dans le répertoire de documents spécifié.

 Configurez les options d'enregistrement au format PDF en créant une instance du`PdfSaveOptions` classe et en définissant les options d'échantillonnage d'image à l'aide de la`DownsampleOptions` propriété. Vous pouvez spécifier la résolution cible des images à l'aide de l'option`Resolution` et définissez un seuil de résolution minimum au-dessus duquel les images ne seront pas réduites à l'aide de la propriété`ResolutionThreshold` propriété.

 Enregistrez le document au format PDF à l'aide du`Save` méthode du`Document` classe spécifiant le chemin et les options de sauvegarde.

#### Q : Quels sont les avantages de réduire la taille d’un document PDF grâce à l’échantillonnage d’images ?
R : Les avantages de la réduction de la taille d’un document PDF grâce à l’échantillonnage d’images sont :

Taille du fichier PDF réduite : l'échantillonnage d'images réduit la résolution des images dans le document PDF, ce qui entraîne une diminution significative de la taille du fichier PDF. Cela facilite le partage et le transfert du fichier, notamment par courrier électronique ou en ligne.

Optimisation de l'espace de stockage : Réduire la taille du fichier PDF permet d'optimiser l'utilisation de l'espace de stockage, surtout lorsque vous disposez de nombreux fichiers PDF contenant des images haute résolution.

Améliorations des performances : les fichiers PDF plus petits se chargent plus rapidement et peuvent être ouverts et visualisés plus rapidement sur différents appareils.