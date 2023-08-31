---
title: Ajouter du texte marqué dans un document Word
linktitle: Ajouter du texte marqué dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter du texte à partir d'un signet dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/append-bookmarked-text/
---

Dans cet article, nous explorerons le code source C# ci-dessus pour comprendre comment utiliser la fonction Ajouter un signet de texte dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet d'ajouter le texte contenu dans un signet spécifique d'un document Word à un autre document.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Obtenir des paragraphes à partir d'un signet

 Avant de commencer à ajouter le texte du signet, nous devons récupérer les paragraphes contenant le début et la fin du signet. Cela peut être fait en accédant au`BookmarkStart` et`BookmarkEnd` propriétés du signet :

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Étape 2 : Vérifiez les paragraphes parents

Nous vérifions si les paragraphes de début et de fin ont des parents valides, c'est-à-dire s'ils appartiennent réellement à un paragraphe. Sinon, nous générons une exception :

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Étape 3 : Vérifier les parents des paragraphes

Nous vérifions si les paragraphes de début et de fin ont le même parent. Sinon, cela signifie que les paragraphes ne sont pas contenus dans la même section ou dans le même document, et nous générons une exception :

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Étape 4 : Copier les paragraphes

Nous parcourons les nœuds (paragraphes) du paragraphe de début au paragraphe de fin. Pour chaque nœud, nous créons une copie et l'importons dans le contexte du document de destination :

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Exemple de code source pour ajouter du texte marqué à l'aide d'Aspose.Words pour .NET

Voici l'exemple complet de code source pour démontrer l'ajout de texte à partir d'un signet à l'aide d'Aspose.Words pour .NET :

```csharp

	// Il s'agit du paragraphe qui contient le début du signet.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Il s'agit du paragraphe qui contient la fin du signet.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Limitons-nous à un scénario raisonnablement simple.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Nous voulons copier tous les paragraphes depuis le paragraphe de début jusqu'au paragraphe de fin (inclus),
	// donc le nœud auquel nous nous arrêtons est celui après le paragraphe de fin.
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

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Ajouter du texte marqué d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour extraire des paragraphes d'un signet, vérifier les parents et copier des paragraphes dans un autre document.

### FAQ pour ajouter du texte mis en signet dans un document Word

#### Q1 : Quelles sont les conditions préalables pour utiliser la fonctionnalité « Ajouter du texte avec des signets » dans Aspose.Words pour .NET ?

R : Pour utiliser la fonction « Ajouter du texte avec des signets » dans Aspose.Words for .NET, vous devez avoir des connaissances de base du langage C#. Vous avez également besoin d'un environnement de développement .NET avec la bibliothèque Aspose.Words installée.

#### Q2 : Comment obtenir les paragraphes contenant le début et la fin d'un signet dans un document Word ?

 R : Pour obtenir les paragraphes contenant le début et la fin d'un signet dans un document Word, vous pouvez accéder au`BookmarkStart` et`BookmarkEnd` propriétés du signet. Voici un exemple de code :

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3 : Que se passe-t-il si les paragraphes de début et de fin n'ont pas de parents valides ?

R : Si les paragraphes de début et de fin n'ont pas de parents valides, c'est-à-dire qu'ils ne sont pas vraiment des paragraphes, une exception sera levée. Cette situation ne peut pas être gérée pour le moment.
