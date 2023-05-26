---
title: Format 1Bpp Indexé
linktitle: Format 1Bpp Indexé
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à formater des images en 1 bpp indexées avec Aspose.Words pour .NET. Tutoriel complet pour les images à faible profondeur de couleur.
type: docs
weight: 10
url: /fr/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
Dans ce tutoriel, nous allons explorer le code source C# fourni pour la fonctionnalité "Format 1Bpp Indexed" avec Aspose.Words pour .NET. Cette fonctionnalité permet de formater les images d'un document au format PNG avec une profondeur de couleur de 1 bit par pixel (1 bpp) et un mode couleur indexé.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Dans cette étape, nous configurons les options de sauvegarde des images. Nous créons un nouveau`ImageSaveOptions`objet précisant le format de sauvegarde souhaité, ici "Png" pour le format PNG. Nous définissons également la page à inclure dans l'image, le mode couleur noir et blanc et le format pixel indexé 1 bpp.

## Étape 4 : sauvegarde des images

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 Dans cette dernière étape, nous enregistrons les images du document au format PNG en utilisant le`Save` et en transmettant le chemin d'accès au fichier de sortie, ainsi que les options d'enregistrement spécifiées.

Vous pouvez maintenant exécuter le code source pour formater les images du document au format PNG avec une profondeur de couleur indexée de 1 bpp. Le fichier résultant sera enregistré dans le répertoire spécifié avec le nom "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Exemple de code source pour le format 1Bpp indexé à l'aide d'Aspose.Words pour .NET

```csharp 
 
			 // Chemin d'accès à votre répertoire de documents
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de format indexé 1Bpp avec Aspose.Words pour .NET. Nous avons appris à formater les images d'un document au format PNG avec une profondeur de couleur de 1 bit par pixel (1 bpp) et un mode couleur indexé.

Cette fonctionnalité est utile lorsque vous souhaitez obtenir des images avec une faible profondeur de couleur et une petite taille de fichier. Le format indexé 1Bpp permet de représenter les images à l'aide d'une palette de couleurs indexées, ce qui peut être bénéfique pour certaines applications spécifiques.

Aspose.Words pour .NET offre un large éventail de fonctionnalités avancées pour la manipulation et la génération de documents. Le format 1Bpp Indexé est l'un des nombreux outils puissants qu'il met à votre disposition.