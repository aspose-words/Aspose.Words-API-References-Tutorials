---
title: Rappel d'enregistrement de page
linktitle: Rappel d'enregistrement de page
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment personnaliser l'enregistrement des pages d'un document dans des images avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-imagesaveoptions/page-saving-callback/
---

Dans ce didacticiel, nous explorerons le code source C# fourni pour utiliser le rappel de sauvegarde de page avec les options de sauvegarde d'image Aspose.Words pour .NET. Cette fonctionnalité vous permet d'effectuer des actions personnalisées lors de l'enregistrement de chaque page d'un document sous forme d'image.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 Dans cette étape, nous configurons les options d'enregistrement de l'image en créant un nouveau`ImageSaveOptions` objet. Nous précisons le format de sauvegarde souhaité, ici « Png » pour le format PNG. Nous utilisons`PageSet` pour préciser la plage de pages à enregistrer, ici de la première page à la dernière page du document (`doc.PageCount - 1`). Nous avons également fixé`PageSavingCallback` à une instance de`HandlePageSavingCallback`, qui est une classe personnalisée pour gérer le rappel de sauvegarde de page.

## Étape 4 : implémentation du rappel de la page de sauvegarde

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implémentez vos actions personnalisées ici
         // Vous pouvez accéder aux informations de la page via la propriété "args.PageIndex".
         // Vous pouvez également modifier les options d'enregistrement pour chaque page individuellement
     }
}
```

 Dans cette étape, nous mettons en œuvre le`HandlePageSavingCallback` classe qui implémente le`IPageSavingCallback` interface. Vous pouvez personnaliser cette classe en ajoutant vos actions spécifiques dans le`PageSaving` méthode. Vous pouvez accéder aux informations de la page via le`args.PageIndex` propriété du`PageSavingArgs` objet passé en argument.

## Étape 5 : Enregistrer les pages sous forme d'images

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 Dans cette dernière étape, nous enregistrons chaque page du document sous forme d'image en utilisant le`Save` méthode et en passant le chemin d'accès au fichier de sortie avec le`.png` extension, ainsi que les options de sauvegarde spécifiées.

Vous pouvez désormais exécuter le code source pour effectuer des actions personnalisées lors de l'enregistrement de chaque page du document en tant qu'image. Le fichier résultant sera enregistré dans le répertoire spécifié sous le nom "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Exemple de code source pour le rappel d'enregistrement de page à l'aide d'Aspose.Words pour .NET


```csharp 
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de rappel d'enregistrement de page avec les options d'enregistrement d'image Aspose.Words pour .NET. Nous avons appris à effectuer des actions personnalisées lors de l'enregistrement de chaque page d'un document sous forme d'image.

Cette fonctionnalité est utile lorsque vous souhaitez effectuer des opérations spécifiques sur chaque page lors de la conversion en images. Vous pouvez accéder aux informations de la page et les utiliser pour personnaliser les options de sauvegarde ou effectuer d'autres traitements spécifiques à la page.

Aspose.Words for .NET offre une large gamme de fonctionnalités avancées pour la manipulation et la génération de documents. Le rappel de page d'enregistrement est l'un des nombreux outils puissants qu'il vous offre pour personnaliser le processus d'enregistrement des pages dans les images.