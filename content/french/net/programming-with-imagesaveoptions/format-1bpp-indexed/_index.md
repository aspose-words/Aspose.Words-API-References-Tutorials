---
title: Format 1Bpp indexé
linktitle: Format 1Bpp indexé
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment convertir un document Word en une image indexée 1 Bpp à l'aide d'Aspose.Words pour .NET. Suivez notre guide étape par étape pour une conversion facile.
type: docs
weight: 10
url: /fr/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## Introduction

Vous êtes-vous déjà demandé comment enregistrer un document Word sous forme d’image en noir et blanc avec seulement quelques lignes de code ? Eh bien, vous avez de la chance ! Aujourd'hui, nous nous penchons sur une petite astuce intéressante utilisant Aspose.Words pour .NET qui vous permet de convertir vos documents en images indexées de 1 Mb/s. Ce format est parfait pour certains types d’archivage numérique, d’impression ou lorsque vous avez besoin de gagner de la place. Nous décomposerons chaque étape pour que ce soit aussi simple que du gâteau. Prêt à commencer? Allons-y !

## Conditions préalables

Avant de mettre la main à la pâte, vous devez mettre en place quelques éléments :

-  Aspose.Words pour .NET : assurez-vous que la bibliothèque est installée. Tu peux[Télécharger les ici](https://releases.aspose.com/words/net/).
- Environnement de développement .NET : Visual Studio est une bonne option, mais vous pouvez utiliser n'importe quel environnement avec lequel vous êtes à l'aise.
- Connaissance de base de C# : Ne vous inquiétez pas, nous allons garder les choses simples, mais un peu de familiarité avec C# sera utile.
- Un document Word : préparez un exemple de document Word à convertir.

## Importer des espaces de noms

Tout d’abord, nous devons importer les espaces de noms nécessaires. Ceci est crucial car cela nous permet d’accéder aux classes et méthodes dont nous avons besoin depuis Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Étape 1 : Configurez votre répertoire de documents

Vous devrez spécifier le chemin d'accès à votre répertoire de documents. C'est ici que votre document Word est stocké et que l'image convertie sera enregistrée.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document Word

 Maintenant, chargeons le document Word dans un Aspose.Words`Document` objet. Cet objet représente votre fichier Word et vous permet de le manipuler.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : configurer les options d'enregistrement de l'image

 Ensuite, nous devons configurer le`ImageSaveOptions`C'est là que la magie opère. Nous allons le configurer pour enregistrer l'image au format PNG avec le mode couleur indexé 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png : Ceci spécifie que nous souhaitons enregistrer le document sous forme d'image PNG.
- PageSet(1) : cela indique que nous convertissons uniquement la première page.
- ImageColorMode.BlackAndWhite : Ceci définit l’image en noir et blanc.
- ImagePixelFormat.Format1bppIndexed : Ceci définit le format de l'image sur 1 Bpp indexé.

## Étape 4 : Enregistrez le document en tant qu'image

 Enfin, nous enregistrons le document sous forme d'image en utilisant le`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Conclusion

Et voila! Avec seulement quelques lignes de code, vous avez transformé votre document Word en une image indexée de 1 Bpp à l'aide d'Aspose.Words pour .NET. Cette méthode est incroyablement utile pour créer des images à contraste élevé et peu encombrantes à partir de vos documents. Désormais, vous pouvez facilement l'intégrer dans vos projets et flux de travail. Bon codage !

## FAQ

### Qu'est-ce qu'une image indexée de 1 Bpp ?
Une image indexée 1 Bpp (1 Bit Per Pixel) est un format d'image en noir et blanc dans lequel chaque pixel est représenté par un seul bit, 0 ou 1. Ce format est très économe en espace.

### Puis-je convertir plusieurs pages d’un document Word à la fois ?
 Oui, vous pouvez. Modifier le`PageSet` propriété dans le`ImageSaveOptions` pour inclure plusieurs pages ou l’intégralité du document.

### Ai-je besoin d’une licence pour utiliser Aspose.Words pour .NET ?
 Oui, Aspose.Words for .NET nécessite une licence pour bénéficier de toutes les fonctionnalités. Vous pouvez obtenir un[permis temporaire ici](https://purchase.aspose.com/temporary-license/).

### Vers quels autres formats d’image puis-je convertir mon document Word ?
 Aspose.Words prend en charge divers formats d'image, notamment JPEG, BMP et TIFF. Changez simplement le`SaveFormat` dans le`ImageSaveOptions`.

### Où puis-je trouver plus de documentation sur Aspose.Words pour .NET ?
 Vous pouvez trouver une documentation détaillée sur le[Page de documentation Aspose.Words pour .NET](https://reference.aspose.com/words/net/).
