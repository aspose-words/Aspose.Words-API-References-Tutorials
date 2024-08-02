---
title: Rapport hauteur/largeur verrouillé
linktitle: Rapport hauteur/largeur verrouillé
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment verrouiller les proportions des formes dans les documents Word à l'aide d'Aspose.Words pour .NET. Suivez ce guide étape par étape pour garder vos images et formes proportionnées.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/aspect-ratio-locked/
---
## Introduction

Vous êtes-vous déjà demandé comment conserver les proportions parfaites des images et des formes dans vos documents Word ? Parfois, vous devez vous assurer que vos images et formes ne sont pas déformées lors du redimensionnement. C’est là que le verrouillage du rapport hauteur/largeur s’avère utile. Dans ce didacticiel, nous verrons comment définir les proportions des formes dans les documents Word à l'aide d'Aspose.Words pour .NET. Nous le décomposerons en étapes faciles à suivre, en veillant à ce que vous puissiez appliquer ces compétences à vos projets en toute confiance.

## Conditions préalables

Avant de plonger dans le code, passons en revue ce dont vous avez besoin pour commencer :

- Bibliothèque Aspose.Words pour .NET : vous devez avoir installé Aspose.Words pour .NET. Si ce n'est pas déjà fait, vous pouvez[Télécharger les ici](https://releases.aspose.com/words/net/).
- Environnement de développement : assurez-vous d'avoir configuré un environnement de développement .NET. Visual Studio est un choix populaire.
- Connaissance de base de C# : Une certaine familiarité avec la programmation C# sera utile.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Ces espaces de noms nous donneront accès aux classes et méthodes dont nous avons besoin pour travailler avec des documents et des formes Word.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Étape 1 : Configurez votre répertoire de documents

 Avant de commencer à manipuler des formes, nous devons créer un répertoire dans lequel nos documents seront stockés. Par souci de simplicité, nous utiliserons un espace réservé`YOUR DOCUMENT DIRECTORY`. Remplacez-le par le chemin réel de votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document

Ensuite, nous allons créer un nouveau document Word à l'aide d'Aspose.Words. Ce document nous servira de canevas pour ajouter des formes et des images.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ici, nous créons une instance du`Document` classe et utiliser un`DocumentBuilder` pour nous aider à construire le contenu du document.

## Étape 3 : Insérer une image

 Maintenant, insérons une image dans notre document. Nous utiliserons le`InsertImage` méthode du`DocumentBuilder`classe. Assurez-vous d'avoir une image dans votre répertoire spécifié.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 Remplacer`dataDir + "Transparent background logo.png"` avec le chemin d'accès à votre fichier image.

## Étape 4 : Verrouiller le rapport hauteur/largeur

Une fois l’image insérée, nous pouvons verrouiller son rapport hauteur/largeur. Le verrouillage du rapport hauteur/largeur garantit que les proportions de l’image restent constantes lors du redimensionnement.

```csharp
shape.AspectRatioLocked = true;
```

 Paramètre`AspectRatioLocked` à`true` garantit que l’image conserve son rapport hauteur/largeur d’origine.

## Étape 5 : Enregistrez le document

Enfin, nous enregistrerons le document dans le répertoire spécifié. Cette étape écrit toutes les modifications que nous avons apportées au fichier de document.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment définir les proportions des formes dans les documents Word à l'aide d'Aspose.Words pour .NET. En suivant ces étapes, vous pouvez vous assurer que vos images et formes conservent leurs proportions, donnant ainsi à vos documents un aspect professionnel et soigné. N'hésitez pas à expérimenter différentes images et formes pour voir comment la fonction de verrouillage des proportions fonctionne dans divers scénarios.

## FAQ

### Puis-je déverrouiller le rapport hauteur/largeur après l'avoir verrouillé ?
Oui, vous pouvez déverrouiller le rapport hauteur/largeur en réglant`shape.AspectRatioLocked = false`.

### Que se passe-t-il si je redimensionne une image avec un rapport hauteur/largeur verrouillé ?
L'image sera redimensionnée proportionnellement, en conservant son rapport largeur/hauteur d'origine.

### Puis-je appliquer cela à d’autres formes que les images ?
Absolument! La fonction de verrouillage des proportions peut être appliquée à n'importe quelle forme, y compris les rectangles, les cercles, etc.

### Aspose.Words pour .NET est-il compatible avec .NET Core ?
Oui, Aspose.Words for .NET prend en charge à la fois .NET Framework et .NET Core.

### Où puis-je trouver plus de documentation sur Aspose.Words pour .NET ?
 Vous pouvez trouver une documentation complète[ici](https://reference.aspose.com/words/net/).