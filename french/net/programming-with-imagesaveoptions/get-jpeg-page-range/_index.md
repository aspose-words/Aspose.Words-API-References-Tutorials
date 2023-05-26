---
title: Obtenir la plage de pages JPEG
linktitle: Obtenir la plage de pages JPEG
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à obtenir une gamme de pages JPEG avec Aspose.Words pour .NET. Tutoriel complet pour extraire des images personnalisées.
type: docs
weight: 10
url: /fr/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

Dans ce didacticiel, nous allons explorer le code source C # fourni pour la fonctionnalité "Get Range of JPEG Pages" avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de convertir une plage spécifique de pages d'un document en images au format JPEG.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words pour .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` méthode et en passant le chemin vers le fichier DOCX à charger.

## Étape 3 : Configurer les options de sauvegarde d'image

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Dans cette étape, nous configurons les options de sauvegarde des images. Nous créons un nouveau`ImageSaveOptions` objet précisant le format de sauvegarde souhaité, ici "Jpeg" pour le format JPEG. Nous définissons également la plage de pages à convertir à l'aide de la`PageSet`objet. Enfin, nous ajustons la luminosité et le contraste de l'image à l'aide de la`ImageBrightness` et`ImageContrast` propriétés, respectivement. Nous modifions également la résolution horizontale à l'aide de la`HorizontalResolution` propriété.

## Étape 4 : sauvegarde des images

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Dans cette dernière étape, nous enregistrons les images de la plage de pages spécifiée au format JPEG à l'aide de la`Save` et en transmettant le chemin d'accès au fichier de sortie, ainsi que les options d'enregistrement spécifiées.

Vous pouvez maintenant exécuter le code source pour convertir une plage spécifique de pages de votre document en images JPEG. Le fichier résultant sera enregistré dans le répertoire spécifié avec le nom "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Exemple de code source pour obtenir la plage de pages Jpeg à l'aide de Aspose.Words pour .NET

```csharp 
 // Chemin d'accès à votre répertoire de documents
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Définissez "PageSet" sur "0" pour convertir uniquement la première page d'un document.
options.PageSet = new PageSet(0);

// Modifiez la luminosité et le contraste de l'image.
// Les deux sont sur une échelle de 0 à 1 et sont à 0,5 par défaut.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Modifiez la résolution horizontale.
// La valeur par défaut de ces propriétés est 96,0, pour une résolution de 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité d'obtention d'une plage de pages JPEG avec Aspose.Words pour .NET. Nous avons appris à convertir une plage spécifique de pages d'un document en images au format JPEG, tout en personnalisant les options d'enregistrement.

Cette fonctionnalité est utile lorsque vous souhaitez extraire des pages spécifiques d'un document et les enregistrer en tant qu'images JPEG. Vous pouvez également régler la luminosité, le contraste et la résolution horizontale des images pour obtenir des résultats personnalisés.

Aspose.Words pour .NET offre une vaste gamme de fonctionnalités avancées pour la manipulation et la génération de documents. Obtenir une plage de pages JPEG est l'un des nombreux outils puissants qu'il met à votre disposition.

N'hésitez pas à intégrer cette fonctionnalité dans vos projets Aspose.Words pour .NET pour obtenir des images JPEG de haute qualité à partir de vos documents.