---
title: Définir la marque d'accentuation de la police
linktitle: Définir la marque d'accentuation de la police
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir des marques d'accentuation de police dans les documents Word à l'aide d'Aspose.Words for .NET avec ce guide détaillé étape par étape. Parfait pour les développeurs .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-font-emphasis-mark/
---
## Introduction

Dans le didacticiel d'aujourd'hui, nous expliquons comment définir les marques d'accentuation des polices dans un document Word à l'aide d'Aspose.Words pour .NET. Que vous cherchiez à souligner un texte spécifique avec une marque unique ou simplement à faire ressortir certains mots, ce guide est là pour vous. Alors, attachez votre ceinture et commençons !

## Conditions préalables

Avant de plonger dans les détails, assurez-vous d’avoir coché les conditions préalables suivantes :

-  Bibliothèque Aspose.Words pour .NET : assurez-vous que la bibliothèque Aspose.Words pour .NET est installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/).
- Environnement de développement : un environnement de développement fonctionnel tel que Visual Studio.
- .NET Framework : assurez-vous que .NET Framework est installé.

## Importer des espaces de noms

Pour travailler avec Aspose.Words for .NET, vous devrez importer les espaces de noms nécessaires. Ajoutez-les en haut de votre fichier de code :

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Maintenant, décomposons le processus en étapes simples. Suivez attentivement chaque étape pour définir les marques d'accentuation de la police dans votre document Word.

## Étape 1 : initialiser le document et DocumentBuilder

Tout d’abord, vous devez initialiser un nouveau document et un DocumentBuilder. La classe DocumentBuilder fournit des méthodes pour insérer du texte et d'autres éléments dans le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiser un nouveau document
Document document = new Document();

// Initialiser DocumentBuilder avec le document
DocumentBuilder builder = new DocumentBuilder(document);
```

## Étape 2 : définir la marque d'accentuation de la police

Une fois DocumentBuilder prêt, vous pouvez maintenant définir la marque d'accentuation de la police. Dans cet exemple, nous utiliserons la marque d'accentuation "UnderSolidCircle".

```csharp
// Définir la marque d'accentuation de la police
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;

// Écrire un texte avec la marque d'accentuation
builder.Write("Emphasis text");
builder.Writeln();
```

## Étape 3 : Effacer le formatage et ajouter du texte normal

Après avoir défini la marque d'accentuation, vous souhaiterez peut-être ajouter du texte normal sans aucune emphase. Pour cela, vous devez effacer le formatage.

```csharp
// Effacer le formatage de la police
builder.Font.ClearFormatting();

// Écrire un texte régulier
builder.Write("Simple text");
```

## Étape 4 : Enregistrez le document

Une fois que vous avez ajouté tout le texte et la mise en forme dont vous avez besoin, la dernière étape consiste à enregistrer le document. Spécifiez le chemin et le nom du fichier où vous souhaitez enregistrer votre document.

```csharp
// Enregistrez le document
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Conclusion

Et voilà ! Définir des marques d'accentuation de police dans un document Word à l'aide d'Aspose.Words pour .NET est aussi simple que cela. Avec seulement quelques lignes de code, vous pouvez faire ressortir votre texte et ajouter une touche professionnelle à vos documents. N'hésitez pas à expérimenter différentes marques d'accentuation et styles en fonction de vos besoins.

## FAQ

### Que sont les marques d’emphase de police ?

Les marques d'accentuation de la police sont des symboles spéciaux ajoutés au texte pour le faire ressortir. Ils peuvent inclure des points, des cercles et d’autres marques décoratives.

### Puis-je utiliser d’autres marques d’accentuation avec Aspose.Words pour .NET ?

 Oui, Aspose.Words for .NET prend en charge diverses marques d'accentuation. Vous pouvez explorer différentes options en vous référant au[documentation](https://reference.aspose.com/words/net/).

### L’utilisation d’Aspose.Words pour .NET est-elle gratuite ?

 Aspose.Words for .NET nécessite une licence pour bénéficier de toutes les fonctionnalités. Vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/) ou acheter une licence[ici](https://purchase.aspose.com/buy).

### Comment puis-je obtenir de l’assistance pour Aspose.Words pour .NET ?

 Vous pouvez obtenir l'assistance de la communauté Aspose et de l'équipe d'assistance en visitant leur[forum d'assistance](https://forum.aspose.com/c/words/8).

### Puis-je utiliser Aspose.Words pour .NET avec d’autres frameworks .NET ?

Oui, Aspose.Words for .NET est compatible avec divers frameworks .NET, notamment .NET Core et .NET 5/6.