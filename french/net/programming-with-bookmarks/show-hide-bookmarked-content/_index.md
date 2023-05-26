---
title: Afficher Masquer le contenu marqué d'un signet
linktitle: Afficher Masquer le contenu marqué d'un signet
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment afficher ou masquer le contenu des signets à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Dans cet article, nous allons explorer le code source C # ci-dessus pour comprendre comment utiliser la fonction Afficher le contenu mis en signet dans Aspose.Words pour la bibliothèque .NET. Cette fonctionnalité vous permet d'afficher ou de masquer le contenu d'un signet en fonction d'une condition spécifique lors de la fusion de données.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Récupérer le marque-page

 Nous utilisons le`Bookmarks` propriété de la plage de documents pour obtenir le signet spécifique dont nous voulons afficher ou masquer le contenu :

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Étape 2 : Insertion des champs de fusion

 Nous utilisons un générateur de documents`DocumentBuilder` pour insérer les champs de fusion nécessaires. Ces champs de fusion définiront une condition pour afficher ou masquer le contenu du signet en fonction de la valeur du`showHide` variable:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Étape 3 : Déplacer le contenu d'un signet

Nous parcourons le contenu du signet et le déplaçons pour qu'il apparaisse

isse avant le signet. Cela contrôlera l'affichage ou le masquage du contenu en fonction de la condition spécifiée :

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Étape 4 : Déplacer le reste du contenu du signet

Nous déplaçons le reste du contenu du signet après le signet, en utilisant le nœud de fin du signet comme point d'insertion :

```csharp
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

## Étape 5 : Effectuer la fusion

 Nous utilisons le`Execute` méthode du document`s `Publipostage` object to execute the merge using the bookmark name and the value of the `AfficherMasquer la variable :

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Exemple de code source pour Afficher Masquer le contenu mis en signet à l'aide de Aspose.Words pour .NET

Voici l'exemple complet de code source pour démontrer l'affichage ou le masquage du contenu des signets à l'aide d'Aspose.Words pour .NET :

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD signet}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité Afficher le contenu mis en signet d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour afficher ou masquer le contenu d'un signet en fonction d'une condition spécifique lors de la fusion de données.