---
title: Obtenir une plage de pages Jpeg
linktitle: Obtenir une plage de pages Jpeg
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment obtenir une gamme de pages JPEG avec Aspose.Words pour .NET. Tutoriel complet pour extraire des images personnalisées.
type: docs
weight: 10
url: /fr/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

Dans ce didacticiel, nous explorerons le code source C# fourni pour la fonctionnalité « Obtenir une plage de pages JPEG » avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de convertir une plage spécifique de pages d'un document en images au format JPEG.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words for .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` et en transmettant le chemin d'accès au fichier DOCX à charger.

## Étape 3 : Configurer les options de sauvegarde d'image

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Dans cette étape, nous configurons les options de sauvegarde des images. Nous créons un nouveau`ImageSaveOptions` objet précisant le format de sauvegarde souhaité, ici "Jpeg" pour le format JPEG. Nous définissons également la plage de pages à convertir à l'aide du`PageSet`objet. Enfin, nous ajustons la luminosité et le contraste de l'image à l'aide du`ImageBrightness`et`ImageContrast` propriétés, respectivement. Nous modifions également la résolution horizontale en utilisant le`HorizontalResolution` propriété.

## Étape 4 : Sauvegarde des images

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Dans cette dernière étape, nous enregistrons les images de la plage de pages spécifiée au format JPEG à l'aide du`Save` et en transmettant le chemin d'accès au fichier de sortie, ainsi que les options de sauvegarde spécifiées.

Vous pouvez désormais exécuter le code source pour convertir une plage spécifique de pages de votre document en images JPEG. Le fichier résultant sera enregistré dans le répertoire spécifié sous le nom "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Exemple de code source pour obtenir une plage de pages Jpeg à l'aide d'Aspose.Words For .NET

```csharp 
 // Chemin d'accès à votre répertoire de documents
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Réglez le "PageSet" sur "0" pour convertir uniquement la première page d'un document.
options.PageSet = new PageSet(0);

// Modifiez la luminosité et le contraste de l'image.
// Les deux sont sur une échelle de 0 à 1 et sont à 0,5 par défaut.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Changez la résolution horizontale.
// La valeur par défaut de ces propriétés est 96,0, pour une résolution de 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité permettant d'obtenir une plage de pages JPEG avec Aspose.Words pour .NET. Nous avons appris à convertir une plage spécifique de pages d'un document en images au format JPEG, tout en personnalisant les options d'enregistrement.

Cette fonctionnalité est utile lorsque vous souhaitez extraire des pages spécifiques d'un document et les enregistrer sous forme d'images JPEG. Vous pouvez également régler la luminosité, le contraste et la résolution horizontale des images pour obtenir des résultats personnalisés.

Aspose.Words for .NET offre une large gamme de fonctionnalités avancées pour la manipulation et la génération de documents. Obtenir une plage de pages JPEG est l'un des nombreux outils puissants qu'il met à votre disposition.

N'hésitez pas à intégrer cette fonctionnalité dans vos projets Aspose.Words for .NET pour obtenir des images JPEG de haute qualité à partir de vos documents.