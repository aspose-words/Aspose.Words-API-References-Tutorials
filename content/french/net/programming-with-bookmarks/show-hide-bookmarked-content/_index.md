---
title: Afficher Masquer le contenu marqué dans un document Word
linktitle: Afficher Masquer le contenu marqué dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment afficher et masquer le contenu mis en signet dans les documents Word à l'aide d'Aspose.Words for .NET avec ce guide détaillé étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Introduction

Prêt à plonger dans le monde de la manipulation de documents avec Aspose.Words pour .NET ? Que vous soyez un développeur cherchant à automatiser les tâches liées aux documents ou simplement une personne curieuse de gérer les fichiers Word par programmation, vous êtes au bon endroit. Aujourd'hui, nous allons explorer comment afficher et masquer le contenu mis en signet dans un document Word à l'aide d'Aspose.Words pour .NET. Ce guide étape par étape fera de vous un pro du contrôle de la visibilité du contenu en fonction des signets. Commençons !

## Conditions préalables

Avant de passer aux choses sérieuses, vous aurez besoin de quelques éléments :

1. Visual Studio : toute version compatible avec .NET.
2.  Aspose.Words pour .NET : téléchargez-le[ici](https://releases.aspose.com/words/net/).
3. Compréhension de base de C# : si vous pouvez écrire un programme simple « Hello World », vous êtes prêt à partir.
4. Un document Word avec des signets : nous utiliserons un exemple de document avec des signets pour ce didacticiel.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Cela garantit que nous disposons de tous les outils dont nous avons besoin pour notre tâche.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Une fois ces espaces de noms en place, nous sommes tous prêts à commencer notre voyage.

## Étape 1 : Configuration de votre projet

Très bien, commençons par configurer notre projet dans Visual Studio.

### Créer un nouveau projet

Ouvrez Visual Studio et créez un nouveau projet d'application console (.NET Core). Nommez-le de manière accrocheuse, comme "BookmarkVisibilityManager".

### Ajouter Aspose.Words pour .NET

Vous devrez ajouter Aspose.Words for .NET à votre projet. Vous pouvez le faire via NuGet Package Manager.

1. Accédez à Outils > Gestionnaire de packages NuGet > Gérer les packages NuGet pour la solution.
2. Recherchez « Aspose.Words ».
3. Installez le paquet.

Super! Maintenant que notre projet est mis en place, passons au chargement de notre document.

## Étape 2 : chargement du document

Nous devons charger le document Word contenant les signets. Pour ce didacticiel, nous utiliserons un exemple de document nommé « Bookmarks.docx ».

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Cet extrait de code définit le chemin d'accès à votre répertoire de documents et charge le document dans le`doc` objet.

## Étape 3 : Afficher/Masquer le contenu mis en favoris

Vient maintenant la partie amusante : afficher ou masquer le contenu en fonction des signets. Nous allons créer une méthode appelée`ShowHideBookmarkedContent` pour gérer ça.

Voici la méthode qui permettra d'activer/désactiver la visibilité du contenu mis en signet :

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Répartition de la méthode

-  Récupération de signets :`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` récupère le signet.
- Traversée de nœuds : nous parcourons les nœuds dans le signet.
-  Bascule de visibilité : si le nœud est un`Run` (une séquence de texte contiguë), nous définissons son`Hidden` propriété.

## Étape 4 : Application de la méthode

Une fois notre méthode en place, appliquons-la pour afficher ou masquer du contenu basé sur un signet.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Cette ligne de code masquera le contenu du signet nommé « MyBookmark1 ».

## Étape 5 : Sauvegarde du document

Enfin, sauvons notre document modifié.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Cela enregistre le document avec les modifications que nous avons apportées.

## Conclusion

Et voilà ! Vous venez d'apprendre à afficher et masquer le contenu mis en signet dans un document Word à l'aide d'Aspose.Words pour .NET. Cet outil puissant facilite la manipulation de documents, que vous automatisiez des rapports, créiez des modèles ou brichiez simplement des fichiers Word. Bon codage !

## FAQ

### Puis-je basculer entre plusieurs favoris à la fois ?
 Oui, vous pouvez appeler le`ShowHideBookmarkedContent` méthode pour chaque signet que vous souhaitez activer.

### Le masquage du contenu affecte-t-il la structure du document ?
Non, masquer du contenu n’affecte que sa visibilité. Le contenu reste dans le document.

### Puis-je utiliser cette méthode pour d’autres types de contenu ?
Cette méthode bascule spécifiquement les exécutions de texte. Pour les autres types de contenu, vous devrez modifier la logique de traversée des nœuds.

### Aspose.Words pour .NET est-il gratuit ?
 Aspose.Words propose un essai gratuit[ici](https://releases.aspose.com/) , mais une licence complète est requise pour une utilisation en production. Vous pouvez l'acheter[ici](https://purchase.aspose.com/buy).

### Comment puis-je obtenir de l'aide si je rencontre des problèmes ?
 Vous pouvez obtenir le soutien de la communauté Aspose[ici](https://forum.aspose.com/c/words/8).