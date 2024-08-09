---
title: Ajouter du texte marqué dans un document Word
linktitle: Ajouter du texte marqué dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter du texte mis en signet dans un document Word à l'aide d'Aspose.Words for .NET avec ce guide étape par étape. Parfait pour les développeurs.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/append-bookmarked-text/
---
## Introduction

Salut! Avez-vous déjà essayé d'ajouter du texte à partir d'une section marquée d'un signet dans un document Word et avez-vous trouvé cela difficile ? Vous avez de la chance ! Ce didacticiel vous guidera tout au long du processus d'utilisation d'Aspose.Words pour .NET. Nous le décomposerons en étapes simples afin que vous puissiez suivre facilement. Plongeons-nous et ajoutons ce texte mis en signet comme un pro !

## Conditions préalables

Avant de commencer, assurons-nous que vous disposez de tout ce dont vous avez besoin :

-  Aspose.Words pour .NET : assurez-vous de l'avoir installé. Sinon, vous pouvez[téléchargez-le ici](https://releases.aspose.com/words/net/).
- Environnement de développement : tout environnement de développement .NET comme Visual Studio.
- Connaissance de base de C# : Comprendre les concepts de base de la programmation C# sera utile.
- Document Word avec signets : un document Word avec des signets configurés, que nous utiliserons pour ajouter du texte.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Cela garantira que nous disposons de tous les outils dont nous avons besoin à portée de main.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Décomposons l'exemple en étapes détaillées.

## Étape 1 : charger le document et initialiser les variables

Très bien, commençons par charger notre document Word et initialiser les variables dont nous aurons besoin.

```csharp
// Chargez les documents source et destination.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Initialisez l'importateur de documents.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Recherchez le signet dans le document source.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Étape 2 : Identifiez les paragraphes de début et de fin

Maintenant, localisons les paragraphes où commence et se termine le signet. Ceci est crucial car nous devons traiter le texte dans ces limites.

```csharp
// Il s'agit du paragraphe qui contient le début du signet.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// Il s'agit du paragraphe qui contient la fin du signet.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## Étape 3 : Valider les parents du paragraphe

Nous devons nous assurer que les paragraphes de début et de fin ont le même parent. Il s’agit d’un scénario simple pour garder les choses simples.

```csharp
// Limitons-nous à un scénario raisonnablement simple.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Étape 4 : Identifiez le nœud à arrêter

Ensuite, nous devons déterminer le nœud où nous arrêterons de copier le texte. Ce sera le nœud immédiatement après le paragraphe de fin.

```csharp
// Nous voulons copier tous les paragraphes depuis le paragraphe de début jusqu'au paragraphe de fin (inclus),
// donc le nœud auquel nous nous arrêtons est celui après le paragraphe de fin.
Node endNode = endPara.NextSibling;
```

## Étape 5 : Ajouter le texte marqué au document de destination

Enfin, parcourons les nœuds du paragraphe de début jusqu'au nœud après le paragraphe de fin, et ajoutons-les au document de destination.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Cela crée une copie du nœud actuel et l'importe (le rend valide) dans le contexte
    // du document de destination. Importer signifie ajuster correctement les styles et les identifiants de liste.
    Node newNode = importer.ImportNode(curNode, true);

    // Ajoutez le nœud importé au document de destination.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Enregistrez le document de destination avec le texte ajouté.
dstDoc.Save("appended_document.docx");
```

## Conclusion

Et voilà ! Vous avez ajouté avec succès le texte d’une section marquée d’un signet dans un document Word à l’aide d’Aspose.Words pour .NET. Cet outil puissant facilite la manipulation de documents et vous avez désormais un tour de plus dans votre sac. Bon codage !

## FAQ

### Puis-je ajouter du texte provenant de plusieurs signets en une seule fois ?
Oui, vous pouvez répéter le processus pour chaque signet et ajouter le texte en conséquence.

### Que se passe-t-il si les paragraphes de début et de fin ont des parents différents ?
L'exemple actuel suppose qu'ils ont le même parent. Pour différents parents, une manipulation plus complexe est nécessaire.

### Puis-je conserver la mise en forme originale du texte ajouté ?
 Absolument! Le`ImportFormatMode.KeepSourceFormatting` garantit que le formatage d’origine est préservé.

### Est-il possible d'ajouter du texte à une position spécifique dans le document de destination ?
Oui, vous pouvez ajouter le texte à n'importe quelle position en accédant au nœud souhaité dans le document de destination.

### Que faire si je dois ajouter le texte d'un signet à une nouvelle section ?
Vous pouvez créer une nouvelle section dans le document de destination et y ajouter le texte.