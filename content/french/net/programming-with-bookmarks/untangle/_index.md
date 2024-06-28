---
title: Démêler dans un document Word
linktitle: Démêler dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à démêler dans un document Word les signets imbriqués dans les lignes de tableau adjacentes à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/untangle/
---

Dans cet article, nous explorerons le code source C# ci-dessus pour comprendre comment utiliser la fonction Untangle dans la bibliothèque Aspose.Words pour .NET. Cette fonction démêle les signets imbriqués qui se trouvent dans les lignes adjacentes du tableau.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Parcourir les signets du document

Nous utilisons une boucle foreach pour parcourir tous les signets présents dans le document :

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Code pour gérer les signets ici
}
```

## Étape 2 : Récupérer les lignes parentales à partir des signets

 Nous utilisons le`GetAncestor` Méthodes pour récupérer les lignes parentes des nœuds de début et de fin du signet :

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Étape 3 : Démêler les signets imbriqués

Si les deux lignes parentes sont trouvées et que le signet commence et se termine dans des lignes adjacentes, nous déplaçons le nœud de fin du signet à la fin du dernier paragraphe de la dernière cellule de la ligne supérieure :

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Exemple de code source pour Untangle utilisant Aspose.Words pour .NET

Voici l'exemple de code source complet pour démêler les signets imbriqués à l'aide d'Aspose.Words pour .NET :

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Obtenez la ligne parent du signet et du nœud de fin du signet.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Si les deux lignes sont correctes et que le début et la fin du signet sont contenus dans des lignes adjacentes,
		// déplacez le nœud de fin du signet à la fin du dernier paragraphe de la dernière cellule de la ligne supérieure.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Untangle d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour démêler les signets imbriqués dans les lignes adjacentes du tableau.

### FAQ

#### Q : La fonction Démêler fonctionne-t-elle uniquement avec les signets imbriqués dans les lignes adjacentes du tableau ?

R : Oui, la fonction Démêler est spécialement conçue pour démêler les signets imbriqués qui se trouvent dans les lignes adjacentes du tableau. Si les signets ne se trouvent pas dans des lignes adjacentes, cette fonction ne sera pas applicable.

#### Q : Comment puis-je identifier les signets imbriqués dans mon document Word ?

R : Vous pouvez identifier les signets imbriqués en parcourant les signets dans le document et en vérifiant si le signet de début et le signet de fin se trouvent dans des lignes adjacentes du tableau. Vous pouvez utiliser le code source fourni dans cet article comme point de départ pour implémenter cette fonctionnalité.

#### Q : La fonction Déchiffrer modifie-t-elle le contenu du document original ?

R : Oui, la fonction Démêler modifie le document original en déplaçant le nœud de fin du signet vers la fin du dernier paragraphe de la dernière cellule de la rangée supérieure. Assurez-vous d'enregistrer une copie de sauvegarde du document avant d'appliquer cette fonctionnalité.

#### Q : Comment puis-je démêler les signets imbriqués dans d'autres types d'éléments de document, tels que des sections ou des paragraphes ?

R : La fonction Démêler présentée dans cet article est spécifiquement conçue pour démêler les signets imbriqués dans les lignes adjacentes du tableau. Si vous souhaitez démêler les signets imbriqués dans d'autres éléments du document, vous devrez adapter le code en conséquence et utiliser les méthodes appropriées pour accéder aux éléments souhaités.

#### Q : Existe-t-il d'autres méthodes pour démêler les signets imbriqués dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : La méthode présentée dans cet article est une méthode courante pour démêler les signets imbriqués dans les lignes de tableau adjacentes. Cependant, il peut exister d'autres approches ou techniques en fonction des besoins spécifiques de votre projet. Vous pouvez consulter le[Références de l'API Aspose.Words pour .NET](https://reference.aspose.com/words/net/) pour explorer davantage les fonctionnalités disponibles.