---
title: Copier le texte marqué dans un document Word
linktitle: Copier le texte marqué dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Copiez sans effort le texte marqué entre des documents Word à l'aide d'Aspose.Words pour .NET. Découvrez comment procéder avec ce guide étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/copy-bookmarked-text/
---
## Introduction

Vous est-il déjà arrivé de devoir copier des sections spécifiques d’un document Word à un autre ? Eh bien, vous avez de la chance ! Dans ce didacticiel, nous vous expliquerons comment copier du texte marqué d'un signet d'un document Word à un autre à l'aide d'Aspose.Words pour .NET. Que vous créiez un rapport dynamique ou automatisiez la génération de documents, ce guide simplifiera le processus pour vous.

## Conditions préalables

Avant de plonger, assurez-vous d’avoir les éléments suivants :

-  Aspose.Words for .NET Library : vous pouvez le télécharger à partir de[ici](https://releases.aspose.com/words/net/).
- Environnement de développement : Visual Studio ou tout autre environnement de développement .NET.
- Connaissance de base de C# : Familiarité avec la programmation C# et le framework .NET.

## Importer des espaces de noms

Pour commencer, assurez-vous d'avoir importé les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## Étape 1 : Charger le document source

Tout d’abord, vous devez charger le document source contenant le texte mis en signet que vous souhaitez copier.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Ici,`dataDir` est le chemin d'accès à votre répertoire de documents, et`Bookmarks.docx` est le document source.

## Étape 2 : Identifiez le signet

Ensuite, identifiez le signet que vous souhaitez copier à partir du document source.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Remplacer`"MyBookmark1"` avec le nom réel de votre signet.

## Étape 3 : Créer le document de destination

Maintenant, créez un nouveau document dans lequel le texte mis en signet sera copié.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Étape 4 : Importer du contenu mis en favoris

 Pour garantir que les styles et la mise en forme sont préservés, utilisez`NodeImporter` pour importer le contenu mis en signet du document source vers le document de destination.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Étape 5 : définir la méthode AppendBookmarkedText

C'est ici que la magie opère. Définissez une méthode pour gérer la copie du texte mis en signet :

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Étape 6 : Enregistrez le document de destination

Enfin, enregistrez le document de destination pour vérifier le contenu copié.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Conclusion

Et c'est tout! Vous avez copié avec succès le texte marqué d'un signet d'un document Word à un autre à l'aide d'Aspose.Words pour .NET. Cette méthode est puissante pour automatiser les tâches de manipulation de documents, rendant votre flux de travail plus efficace et rationalisé.

## FAQ

### Puis-je copier plusieurs favoris à la fois ?
Oui, vous pouvez parcourir plusieurs signets et utiliser la même méthode pour copier chacun d’eux.

### Que se passe-t-il si le signet n'est pas trouvé ?
 Le`Range.Bookmarks` la propriété reviendra`null`, alors assurez-vous de gérer ce cas pour éviter les exceptions.

### Puis-je conserver la mise en forme du signet original ?
 Absolument! En utilisant`ImportFormatMode.KeepSourceFormatting` garantit que le formatage d’origine est préservé.

### Y a-t-il une limite à la taille du texte mis en signet ?
Il n'y a pas de limite spécifique, mais les performances peuvent varier avec des documents extrêmement volumineux.

### Puis-je copier du texte entre différents formats de documents Word ?
Oui, Aspose.Words prend en charge différents formats Word et la méthode fonctionne dans ces formats.