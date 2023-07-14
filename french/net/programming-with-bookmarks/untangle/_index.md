---
title: Démêler dans un document Word
linktitle: Démêler dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à démêler les signets imbriqués dans un document Word dans des lignes de tableau adjacentes à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/untangle/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Untangle dans la bibliothèque Aspose.Words pour .NET. Cette fonction dénoue les signets imbriqués qui se trouvent dans les lignes de tableau adjacentes.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Parcourir les signets du document

Nous utilisons une boucle foreach pour parcourir tous les signets présents dans le document :

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Code de gestion des signets ici
}
```

## Étape 2 : Obtenir les lignes parentes des signets

 Nous utilisons le`GetAncestor`méthodes pour récupérer les lignes parentes des nœuds de début et de fin du signet :

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Étape 3 : démêler les signets imbriqués

Si les deux lignes parentes sont trouvées et que le signet commence et se termine dans des lignes adjacentes, nous déplaçons le nœud de fin du signet à la fin du dernier paragraphe de la dernière cellule de la rangée supérieure :

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Exemple de code source pour Untangle utilisant Aspose.Words pour .NET

Voici l'exemple de code source complet pour démêler les signets imbriqués à l'aide de Aspose.Words pour .NET :

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Obtenez la ligne parent du signet et du nœud de fin de signet.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Si les deux lignes sont correctes et que le début et la fin du signet sont contenus dans des lignes adjacentes,
		// déplacer le nœud de fin de signet à la fin du dernier paragraphe de la dernière cellule de la ligne supérieure.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Untangle d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour démêler les signets imbriqués dans les lignes de tableau adjacentes.

### FAQ

#### Q : La fonction Démêler ne fonctionne-t-elle qu'avec des signets imbriqués dans des lignes de tableau adjacentes ?

R : Oui, la fonction Démêler est conçue spécifiquement pour démêler les signets imbriqués qui se trouvent dans des lignes de tableau adjacentes. Si les signets ne sont pas dans des lignes adjacentes, cette fonction ne sera pas applicable.

#### Q : Comment puis-je identifier les signets imbriqués dans mon document Word ?

R : Vous pouvez identifier les signets imbriqués en parcourant les signets du document et en vérifiant si le signet de début et le signet de fin se trouvent dans des lignes de tableau adjacentes. Vous pouvez utiliser le code source fourni dans cet article comme point de départ pour implémenter cette fonctionnalité.

#### Q : La fonction Déchiffrer modifie-t-elle le contenu du document d'origine ?

R : Oui, la fonction Démêler modifie le document d'origine en déplaçant le nœud de fin du signet à la fin du dernier paragraphe de la dernière cellule de la rangée supérieure. Assurez-vous d'enregistrer une copie de sauvegarde du document avant d'appliquer cette fonctionnalité.

#### Q : Comment puis-je démêler les signets imbriqués dans d'autres types d'éléments de document, tels que des sections ou des paragraphes ?

R : La fonction Démêler présentée dans cet article est spécialement conçue pour démêler les signets imbriqués dans les lignes de tableau adjacentes. Si vous souhaitez démêler les signets imbriqués dans d'autres éléments du document, vous devrez adapter le code en conséquence et utiliser les méthodes appropriées pour accéder aux éléments souhaités.

#### Q : Existe-t-il d'autres méthodes pour démêler les signets imbriqués dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : La méthode présentée dans cet article est une méthode courante pour démêler les signets imbriqués dans les lignes de tableau adjacentes. Cependant, il peut y avoir d'autres approches ou techniques selon les besoins spécifiques de votre projet. Vous pouvez consulter la documentation officielle d'Aspose.Words pour explorer davantage les fonctionnalités disponibles.