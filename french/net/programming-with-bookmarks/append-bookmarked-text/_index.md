---
title: Ajouter le texte marqué d'un signet
linktitle: Ajouter le texte marqué d'un signet
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajouter du texte à partir d'un signet dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/append-bookmarked-text/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Ajouter un texte mis en signet dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet d'ajouter le texte contenu dans un signet spécifique d'un document Word à un autre document.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Obtenir des paragraphes à partir d'un signet

 Avant de commencer à ajouter le texte du signet, nous devons obtenir les paragraphes contenant le début et la fin du signet. Cela peut être fait en accédant au`BookmarkStart` et`BookmarkEnd` propriétés du signet :

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Étape 2 : Vérifier les paragraphes parents

Nous vérifions si les paragraphes de début et de fin ont des parents valides, c'est-à-dire s'ils appartiennent vraiment à un paragraphe. Sinon, nous générons une exception :

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Étape 3 : Vérifier les parents des paragraphes

Nous vérifions si les paragraphes de début et de fin ont le même parent. Si ce n'est pas le cas, cela signifie que les paragraphes ne sont pas contenus dans la même section ou le même document, et nous levons une exception :

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Étape 4 : Copiez les paragraphes

Nous parcourons les nœuds (paragraphes) du paragraphe de début au paragraphe de fin. Pour chaque nœud, nous créons une copie et l'importons dans le contexte du document de destination :

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Exemple de code source pour ajouter du texte mis en signet à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer l'ajout de texte à partir d'un signet à l'aide de Aspose.Words pour .NET :

```csharp

	// Il s'agit du paragraphe qui contient le début du signet.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// C'est le paragraphe qui contient la fin du signet.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Limitons-nous à un scénario raisonnablement simple.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Nous voulons copier tous les paragraphes du paragraphe de début jusqu'au (et y compris) le paragraphe de fin,
	// donc le nœud auquel nous nous arrêtons est un après le dernier paragraphe.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// Cela crée une copie du nœud actuel et l'importe (le rend valide) dans le contexte
		// du document de destination. Importer signifie ajuster correctement les styles et les identifiants de liste.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Append Bookmarked Text de Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour obtenir des paragraphes à partir d'un signet, vérifier les parents et copier des paragraphes dans un autre document.