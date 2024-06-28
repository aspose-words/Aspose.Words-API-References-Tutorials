---
title: Afficher Masquer le contenu marqué dans un document Word
linktitle: Afficher Masquer le contenu marqué dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment afficher ou masquer dynamiquement le contenu mis en signet dans des documents Word à l'aide d'Aspose.Words for .NET avec ce guide complet étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Introduction

Salut! Avez-vous déjà souhaité contrôler la visibilité d'un contenu spécifique dans un document Word en fonction de certaines conditions ? Avec Aspose.Words pour .NET, vous pouvez afficher ou masquer dynamiquement le contenu mis en signet avec seulement quelques lignes de code. Dans ce didacticiel, je vais vous guider pas à pas tout au long du processus, en m'assurant que vous comprenez chaque partie du code. À la fin, vous serez un pro dans la manipulation des signets dans les documents Word. Commençons!

## Conditions préalables

Avant de plonger dans le didacticiel, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1. Connaissance de base de C# : Vous devez être à l'aise avec la syntaxe et les concepts C#.
2.  Aspose.Words pour .NET : téléchargez-le[ici](https://releases.aspose.com/words/net/) . Si vous n'êtes pas prêt à acheter, vous pouvez commencer par un[essai gratuit](https://releases.aspose.com/).
3. Visual Studio : toute version récente fonctionnera, mais il est recommandé d'utiliser la dernière version.
4. .NET Framework : assurez-vous qu'il est installé sur votre ordinateur.

Prêt à commencer? Super! Commençons par importer les espaces de noms nécessaires.

## Importer des espaces de noms

Pour utiliser Aspose.Words pour .NET, nous devons importer les espaces de noms requis. Cette étape garantit que nous avons accès à toutes les classes et méthodes que nous utiliserons.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Ces espaces de noms sont cruciaux pour travailler avec des documents Word et manipuler leur contenu.

## Étape 1 : configuration du document

Commençons par créer un nouveau document Word et un générateur de documents. Le générateur de documents nous aide à ajouter et à manipuler facilement du contenu dans le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Dans cette étape, nous initialisons un nouveau document et un générateur de documents. Cela prépare notre environnement pour d’autres opérations.

## Étape 2 : ajout de contenu mis en favoris

Ensuite, nous ajouterons du contenu au document et créerons un signet autour de celui-ci. Ce signet nous aidera à identifier et à manipuler le contenu.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Ici, nous ajoutons du texte avant et après le contenu mis en signet. Le`StartBookmark` et`EndBookmark` les méthodes définissent les limites du signet.

## Étape 3 : Insertion d'un champ conditionnel

Pour contrôler la visibilité du contenu mis en signet, nous utiliserons un champ conditionnel. Ce champ vérifiera une condition et affichera ou masquera le contenu en conséquence.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

Dans cette étape, nous insérons un champ IF qui vérifie la valeur du signet. Si la valeur est « vrai », elle affichera « Visible » ; sinon, il affichera « Caché ».

## Étape 4 : Réorganiser les nœuds

Ensuite, nous devons réorganiser les nœuds pour garantir que la logique conditionnelle s'applique correctement au contenu mis en signet.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Ici, nous déplaçons les nœuds pour nous assurer que la condition englobe correctement le contenu mis en signet.

## Étape 5 : Exécution du publipostage

Enfin, nous exécuterons un publipostage pour définir la valeur du signet et déterminer si le contenu doit être affiché ou masqué.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Cette étape définit la valeur du signet sur "true", ce qui rendra le contenu visible en fonction de notre condition.

## Étape 6 : Sauvegarde du document

Après toutes les manipulations, la dernière étape consiste à sauvegarder le document modifié.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Ici, nous enregistrons le document avec un nom de fichier descriptif pour indiquer les modifications.

## Conclusion

 Et c'est tout! Vous avez appris avec succès comment afficher ou masquer le contenu mis en signet dans un document Word à l'aide d'Aspose.Words pour .NET. Ce didacticiel a couvert la création d'un document, l'ajout de signets, l'insertion de champs conditionnels, la réorganisation des nœuds et l'exécution d'un publipostage. Aspose.Words offre une pléthore de fonctionnalités, alors n'hésitez pas à explorer les[Documentation API](https://reference.aspose.com/words/net/) pour des capacités plus avancées.

## FAQ

### 1. Qu'est-ce qu'Aspose.Words pour .NET ?

Aspose.Words for .NET est une bibliothèque puissante qui permet aux développeurs de créer, modifier et convertir des documents Word par programme. Il est largement utilisé pour les tâches d'automatisation des documents.

### 2. Puis-je utiliser Aspose.Words pour .NET gratuitement ?

 Vous pouvez essayer Aspose.Words pour .NET en utilisant un[essai gratuit](https://releases.aspose.com/). Pour une utilisation à long terme, vous devrez acheter une licence.

### 3. Comment modifier d'autres propriétés d'un signet ?

 Aspose.Words vous permet de manipuler diverses propriétés d'un signet, telles que son texte et son emplacement. Se référer au[Documentation API](https://reference.aspose.com/words/net/) pour des instructions détaillées.

### 4. Comment puis-je obtenir de l'aide pour Aspose.Words pour .NET ?

Vous pouvez obtenir de l'aide en visitant le[Forum d'assistance Aspose](https://forum.aspose.com/c/words/8).

### 5. Puis-je manipuler d’autres types de contenu avec Aspose.Words for .NET ?

Oui, Aspose.Words for .NET prend en charge différents types de manipulation de contenu, notamment du texte, des images, des tableaux, etc.