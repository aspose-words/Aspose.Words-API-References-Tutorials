---
title: Rappel d'enregistrement de page
linktitle: Rappel d'enregistrement de page
second_title: API de traitement de documents Aspose.Words
description: Apprenez à personnaliser l'enregistrement de pages de document en images avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-imagesaveoptions/page-saving-callback/
---

Dans ce didacticiel, nous allons explorer le code source C # fourni pour utiliser le rappel d'enregistrement de page avec les options d'enregistrement d'image Aspose.Words pour .NET. Cette fonctionnalité vous permet d'effectuer des actions personnalisées lors de l'enregistrement de chaque page d'un document en tant qu'image.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 Dans cette étape, nous configurons les options d'enregistrement d'image en créant un nouveau`ImageSaveOptions` objet. On précise le format de sauvegarde souhaité, ici "Png" pour le format PNG. Nous utilisons`PageSet` de spécifier la plage de pages à enregistrer, ici de la première page à la dernière page du document (`doc.PageCount - 1`). Nous fixons également`PageSavingCallback` à une instance de`HandlePageSavingCallback`, qui est une classe personnalisée pour gérer le rappel d'enregistrement de page.

## Étape 4 : Implémenter le rappel de la page de sauvegarde

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Mettez en œuvre vos actions personnalisées ici
         // Vous pouvez accéder aux informations de la page via la propriété "args.PageIndex"
         // Vous pouvez également modifier les options de sauvegarde pour chaque page individuellement
     }
}
```

 Dans cette étape, nous implémentons la`HandlePageSavingCallback` classe qui implémente`IPageSavingCallback` interface. Vous pouvez personnaliser cette classe en ajoutant vos actions spécifiques dans le`PageSaving` méthode. Vous pouvez accéder aux informations de la page via le`args.PageIndex` propriété de la`PageSavingArgs` objet passé en argument.

## Étape 5 : Enregistrer des pages en tant qu'images

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 Dans cette dernière étape, nous enregistrons chaque page du document sous forme d'image à l'aide de la`Save` méthode et en passant le chemin vers le fichier de sortie avec la`.png` extension, ainsi que les options d'enregistrement spécifiées.

Vous pouvez maintenant exécuter le code source pour effectuer des actions personnalisées lors de l'enregistrement de chaque page du document en tant qu'image. Le fichier résultant sera enregistré dans le répertoire spécifié avec le nom "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Exemple de code source pour le rappel d'enregistrement de page à l'aide de Aspose.Words pour .NET


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

Dans ce didacticiel, nous avons exploré la fonctionnalité de rappel d'enregistrement de page avec les options d'enregistrement d'image Aspose.Words pour .NET. Nous avons appris à effectuer des actions personnalisées lors de l'enregistrement de chaque page d'un document en tant qu'image.

Cette fonctionnalité est utile lorsque vous souhaitez effectuer des opérations spécifiques sur chaque page lors de la conversion en images. Vous pouvez accéder aux informations de page et les utiliser pour personnaliser les options de sauvegarde ou effectuer d'autres traitements spécifiques à la page.

Aspose.Words pour .NET offre une vaste gamme de fonctionnalités avancées pour la manipulation et la génération de documents. Le rappel d'enregistrement de page est l'un des nombreux outils puissants qu'il vous offre pour personnaliser le processus d'enregistrement des pages en images.