---
title: Ancrage vertical
linktitle: Ancrage vertical
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir les positions d'ancrage verticales des zones de texte dans les documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape facile inclus.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/vertical-anchor/
---
## Introduction

Avez-vous déjà eu besoin de contrôler exactement où le texte apparaît dans une zone de texte dans un document Word ? Peut-être souhaitez-vous que votre texte soit ancré en haut, au milieu ou en bas de la zone de texte ? Si c'est le cas, vous êtes au bon endroit ! Dans ce didacticiel, nous verrons comment utiliser Aspose.Words for .NET pour définir l'ancrage vertical des zones de texte dans les documents Word. Considérez l’ancrage vertical comme une baguette magique qui positionne votre texte précisément là où vous le souhaitez dans son conteneur. Prêt à plonger ? Commençons !

## Conditions préalables

Avant de plonger dans les rouages de l’ancrage vertical, vous devez avoir quelques éléments en place :

1.  Aspose.Words for .NET : assurez-vous que la bibliothèque Aspose.Words for .NET est installée. Si vous ne l'avez pas encore, vous pouvez[téléchargez-le ici](https://releases.aspose.com/words/net/).
2. Visual Studio : ce didacticiel suppose que vous utilisez Visual Studio ou un autre IDE .NET pour le codage.
3. Connaissance de base de C# : La familiarité avec C# et .NET vous aidera à suivre en douceur.

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires dans votre code C#. C'est ici que vous indiquez à votre application où trouver les classes et les méthodes que vous utiliserez. Voici comment procéder :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Ces espaces de noms fournissent les classes dont vous aurez besoin pour travailler avec des documents et des formes.

## Étape 1 : initialiser le document

Tout d’abord, vous devez créer un nouveau document Word. Considérez cela comme la configuration de votre toile avant de commencer à peindre.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ici,`Document` est ta toile vierge, et`DocumentBuilder` est votre pinceau, vous permettant d'ajouter des formes et du texte.

## Étape 2 : Insérer une forme TextBox

Maintenant, ajoutons une zone de texte à notre document. C'est ici que vivra votre texte. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 Dans cet exemple,`ShapeType.TextBox` spécifie la forme souhaitée, et`200, 200` sont la largeur et la hauteur de la zone de texte en points.

## Étape 3 : définir l'ancrage vertical

C'est ici que la magie opère ! Vous pouvez définir l'alignement vertical du texte dans la zone de texte. Cela détermine si le texte est ancré en haut, au milieu ou en bas de la zone de texte.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 Dans ce cas,`TextBoxAnchor.Bottom`garantit que le texte sera ancré au bas de la zone de texte. Si vous vouliez qu'il soit centré ou aligné vers le haut, vous utiliseriez`TextBoxAnchor.Center` ou`TextBoxAnchor.Top`, respectivement.

## Étape 4 : ajouter du texte à la zone de texte

Il est maintenant temps d'ajouter du contenu à votre zone de texte. Pensez-y comme au remplissage de votre toile avec la touche finale.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 Ici,`MoveTo` garantit que le texte est inséré dans la zone de texte, et`Write` ajoute le texte réel.

## Étape 5 : Enregistrez le document

La dernière étape consiste à enregistrer votre document. C'est comme mettre votre tableau fini dans un cadre.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## Conclusion

Et voilà ! Vous venez d'apprendre à contrôler l'alignement vertical du texte dans une zone de texte dans un document Word à l'aide d'Aspose.Words pour .NET. Que vous ancriez le texte en haut, au centre ou en bas, cette fonctionnalité vous donne un contrôle précis sur la mise en page de votre document. Ainsi, la prochaine fois que vous aurez besoin de modifier l'emplacement du texte de votre document, vous saurez exactement quoi faire !

## FAQ

### Qu’est-ce que l’ancrage vertical dans un document Word ?
Contrôles d'ancrage vertical où le texte est positionné dans une zone de texte, comme l'alignement en haut, au milieu ou en bas.

### Puis-je utiliser d’autres formes que les zones de texte ?
Oui, vous pouvez utiliser l’ancrage vertical avec d’autres formes, bien que les zones de texte constituent le cas d’utilisation le plus courant.

### Comment changer le point d’ancrage après avoir créé la zone de texte ?
 Vous pouvez modifier le point d'ancrage en définissant le`VerticalAnchor` propriété sur l’objet de forme de zone de texte.

### Est-il possible d'ancrer le texte au milieu de la zone de texte ?
 Absolument! Utilisez simplement`TextBoxAnchor.Center` pour centrer le texte verticalement dans la zone de texte.

### Où puis-je trouver plus d’informations sur Aspose.Words pour .NET ?
 Découvrez le[Documentation Aspose.Words](https://reference.aspose.com/words/net/) pour plus de détails et de guides.