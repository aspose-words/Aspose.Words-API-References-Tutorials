---
title: Rappel d'enregistrement de page
linktitle: Rappel d'enregistrement de page
second_title: API de traitement de documents Aspose.Words
description: Apprenez à enregistrer chaque page d'un document Word en tant qu'image PNG distincte à l'aide d'Aspose.Words pour .NET grâce à notre guide détaillé étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-imagesaveoptions/page-saving-callback/
---
## Introduction

Salut! Avez-vous déjà ressenti le besoin d'enregistrer chaque page d'un document Word sous forme d'images distinctes ? Peut-être souhaitez-vous décomposer un rapport volumineux en visuels faciles à digérer, ou peut-être avez-vous besoin de créer des vignettes pour un aperçu. Quelle que soit votre raison, l'utilisation d'Aspose.Words pour .NET rend cette tâche un jeu d'enfant. Dans ce guide, nous vous guiderons tout au long du processus de configuration d'un rappel d'enregistrement de page pour enregistrer chaque page d'un document en tant qu'image PNG individuelle. Allons-y !

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Words for .NET : si vous ne l'avez pas déjà fait, téléchargez-le et installez-le à partir de[ici](https://releases.aspose.com/words/net/).
2. Visual Studio : n'importe quelle version devrait fonctionner, mais j'utiliserai Visual Studio 2019 pour ce guide.
3. Connaissance de base de C# : vous aurez besoin d’une compréhension de base de C# pour suivre.

## Importer des espaces de noms

Tout d’abord, nous devons importer les espaces de noms nécessaires. Cela nous aide à accéder aux classes et méthodes requises sans taper l'espace de noms complet à chaque fois.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Étape 1 : Configurez votre répertoire de documents

Très bien, commençons par définir le chemin d'accès à votre répertoire de documents. C'est ici que se trouve votre document Word d'entrée et où les images de sortie seront enregistrées.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez votre document

Ensuite, nous chargerons le document que vous souhaitez traiter. Assurez-vous que votre document ("Rendering.docx") se trouve dans le répertoire spécifié.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : configurer les options d'enregistrement de l'image

Nous devons configurer les options de sauvegarde des images. Dans ce cas, nous enregistrons les pages sous forme de fichiers PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 Ici,`PageSet` spécifie la plage de pages à enregistrer, et`PageSavingCallback` pointe vers notre classe de rappel personnalisée.

## Étape 4 : implémenter le rappel d'enregistrement de page

Maintenant, implémentons la classe de rappel qui gère la façon dont chaque page est enregistrée.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 Cette classe implémente le`IPageSavingCallback` interface, et dans l'interface`PageSaving` méthode, nous définissons le modèle de dénomination pour chaque page enregistrée.

## Étape 5 : Enregistrez le document sous forme d'images

Enfin, nous enregistrons le document en utilisant les options configurées.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Conclusion

Et voilà ! Vous avez configuré avec succès un rappel d'enregistrement de page pour enregistrer chaque page d'un document Word en tant qu'image PNG distincte à l'aide d'Aspose.Words pour .NET. Cette technique est incroyablement utile pour diverses applications, depuis la création d'aperçus de pages jusqu'à la génération d'images de pages individuelles pour les rapports. 

Bon codage !

## FAQ

### Puis-je enregistrer des pages dans des formats autres que PNG ?  
 Oui, vous pouvez enregistrer des pages dans différents formats tels que JPEG, BMP et TIFF en modifiant le`SaveFormat` dans`ImageSaveOptions`.

### Que faire si je souhaite enregistrer uniquement des pages spécifiques ?  
 Vous pouvez spécifier les pages que vous souhaitez enregistrer en ajustant le`PageSet` paramètre dans`ImageSaveOptions`.

### Est-il possible de personnaliser la qualité de l'image ?  
 Absolument! Vous pouvez définir des propriétés telles que`ImageSaveOptions.JpegQuality` pour contrôler la qualité des images de sortie.

### Comment puis-je gérer efficacement des documents volumineux ?  
Pour les documents volumineux, envisagez de traiter les pages par lots pour gérer efficacement l'utilisation de la mémoire.

### Où puis-je trouver plus d’informations sur Aspose.Words pour .NET ?  
 Découvrez le[documentation](https://reference.aspose.com/words/net/) pour des guides et des exemples complets.