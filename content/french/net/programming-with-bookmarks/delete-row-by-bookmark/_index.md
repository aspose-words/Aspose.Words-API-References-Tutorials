---
title: Supprimer la ligne par signet dans un document Word
linktitle: Supprimer la ligne par signet dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment supprimer une ligne de tableau en fonction d'un signet spécifique dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Dans cet article, nous explorerons le code source C# ci-dessus pour comprendre comment utiliser la fonction Supprimer la ligne par signet dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet de supprimer une ligne de tableau en fonction d'un signet spécifique dans un document Word.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Obtenir le signet

 Nous utilisons le`Bookmarks` propriété de la plage de documents pour obtenir le signet spécifique que nous souhaitons utiliser pour supprimer la ligne du tableau :

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Étape 2 : suppression de la ligne du tableau

 Nous utilisons le`GetAncestor` méthode pour obtenir le`Row` tapez l'élément parent du signet. Ensuite, nous utilisons le`Remove` méthode pour supprimer la ligne du tableau :

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Exemple de code source pour Supprimer une ligne par signet à l'aide d'Aspose.Words pour .NET

Voici l'exemple complet de code source pour démontrer la suppression d'une ligne de tableau basée sur un signet spécifique à l'aide d'Aspose.Words pour .NET :

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Supprimer la ligne par signet d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour supprimer une ligne de tableau en fonction d'un signet spécifique dans un document.

### FAQ pour supprimer une ligne par signet dans un document Word

#### Q : Puis-je supprimer plusieurs lignes en utilisant le même signet ?

R : Oui, vous pouvez supprimer plusieurs lignes en utilisant le même signet. Cependant, vous devez gérer la logique de votre code pour déterminer le nombre de lignes à supprimer et apporter les ajustements nécessaires à l'extrait de code fourni.

#### Q : Que se passe-t-il si le signet n'existe pas dans le document ?

R : Si le signet spécifié n'existe pas dans le document, l'extrait de code renverra une valeur nulle pour l'objet signet. Par conséquent, vous devez gérer ce scénario dans votre code en ajoutant les vérifications appropriées avant de tenter de supprimer la ligne du tableau.

#### Q : La bibliothèque Aspose.Words est-elle gratuite ?

 R : La bibliothèque Aspose.Words est une bibliothèque commerciale et vous aurez peut-être besoin d'une licence valide pour l'utiliser dans vos projets. Vous pouvez visiter le[Références de l'API Aspose.Words pour .NET](https://reference.aspose.com/words/net/) pour en savoir plus sur leurs options de licence et leurs tarifs.

#### Q : Puis-je supprimer des lignes d’un tableau dans une section spécifique du document Word ?

R : Oui, vous pouvez supprimer des lignes d'un tableau dans une section spécifique d'un document Word. Vous pouvez modifier l'extrait de code fourni pour cibler une section spécifique en utilisant la plage ou le signet approprié dans cette section.