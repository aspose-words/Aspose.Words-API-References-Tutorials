---
title: Réduisez la taille du document PDF grâce au sous-échantillonnage des images
linktitle: Réduisez la taille du document PDF grâce au sous-échantillonnage des images
second_title: API de traitement de documents Aspose.Words
description: Réduisez la taille du document PDF en sous-échantillonnant les images à l’aide d’Aspose.Words for .NET. Optimisez vos PDF pour des temps de chargement et de téléchargement plus rapides.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/downsampling-images/
---
## Introduction

Les PDF sont un incontournable du monde numérique, utilisés pour tout, du partage de documents à la création de livres électroniques. Cependant, leur taille peut parfois constituer un obstacle, notamment lorsqu’il s’agit de contenus riches en images. C’est là que le sous-échantillonnage des images entre en jeu. En réduisant la résolution des images dans le PDF, vous pouvez réduire considérablement la taille du fichier sans trop compromettre la qualité. Dans ce didacticiel, nous passerons en revue les étapes pour y parvenir à l'aide d'Aspose.Words for .NET.

## Conditions préalables

Avant de passer au code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1.  Aspose.Words pour .NET : assurez-vous que la bibliothèque Aspose.Words est installée. Sinon, vous pouvez le télécharger[ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : tout environnement de développement .NET comme Visual Studio.
3. Connaissance de base de C# : Comprendre les bases de la programmation C# sera utile.
4.  Un exemple de document : un document Word (par exemple,`Rendering.docx`) avec des images à convertir en PDF.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires. Ajoutez-les en haut de votre fichier de code :

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Maintenant, décomposons le processus en étapes gérables.

## Étape 1 : Charger le document

La première étape consiste à charger votre document Word. C'est ici que vous spécifiez le chemin d'accès à votre répertoire de documents.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Dans cette étape, nous chargeons le document Word à partir du répertoire spécifié. Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin réel où se trouve votre document.

## Étape 2 : configurer les options de sous-échantillonnage

Ensuite, nous devons configurer les options de sous-échantillonnage. Cela implique de définir la résolution et le seuil de résolution des images.

```csharp
// Nous pouvons définir un seuil minimum de sous-échantillonnage.
// Cette valeur empêchera le sous-échantillonnage de la deuxième image du document d’entrée.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Ici, nous créons une nouvelle instance de`PdfSaveOptions` et en définissant le`Resolution` à 36 DPI et le`ResolutionThreshold` à 128 DPI. Cela signifie que toute image avec une résolution supérieure à 128 DPI sera sous-échantillonnée à 36 DPI.

## Étape 3 : Enregistrez le document au format PDF

Enfin, nous enregistrons le document au format PDF avec les options configurées.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Dans cette dernière étape, nous enregistrons le document au format PDF dans le même répertoire avec les options de sous-échantillonnage spécifiées.

## Conclusion

Et voila! Vous avez réussi à réduire la taille de votre PDF en sous-échantillonnant les images à l'aide d'Aspose.Words pour .NET. Cela rend non seulement vos PDF plus faciles à gérer, mais permet également des téléchargements plus rapides et des expériences de visualisation plus fluides.

## FAQ

### Qu’est-ce que le sous-échantillonnage ?
Le sous-échantillonnage est le processus de réduction de la résolution des images, ce qui contribue à réduire la taille des fichiers des documents contenant ces images.

### Le sous-échantillonnage affectera-t-il la qualité des images ?
Oui, le sous-échantillonnage réduira la qualité de l’image. Cependant, l'impact dépend du degré de réduction de la résolution. C'est un compromis entre la taille du fichier et la qualité de l'image.

### Puis-je choisir les images à sous-échantillonner ?
 Oui, en définissant le`ResolutionThreshold`, vous pouvez contrôler quelles images sont sous-échantillonnées en fonction de leur résolution d'origine.

### Quelle est la résolution idéale pour le sous-échantillonnage ?
La résolution idéale dépend de vos besoins spécifiques. Généralement, 72 DPI sont utilisés pour les images Web, tandis que des résolutions plus élevées sont utilisées pour la qualité d'impression.

### Aspose.Words pour .NET est-il gratuit ?
 Aspose.Words for .NET est un produit commercial, mais vous pouvez télécharger un essai gratuit[ici](https://releases.aspose.com/) ou demander un[permis temporaire](https://purchase.aspose.com/temporary-license/).