---
title: Afficher Masquer le contenu mis en signet dans le document Word
linktitle: Afficher Masquer le contenu mis en signet dans le document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à afficher ou à masquer le contenu des signets dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Dans cet article, nous allons explorer le code source C # ci-dessus pour comprendre comment utiliser la fonction Afficher le contenu mis en signet dans Aspose.Words pour la bibliothèque .NET. Cette fonctionnalité vous permet d'afficher ou de masquer le contenu d'un signet dans un document Word en fonction d'une condition spécifique lors de la fusion de données.

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

### FAQ pour afficher le contenu marqué d'un signet dans un document Word

#### Q : Puis-je utiliser la même condition pour plusieurs signets dans le même document ?

 R : Oui, vous pouvez utiliser la même condition pour plusieurs signets dans le même document. Répétez simplement les étapes 2 à 5 pour chaque signet, en ajustant le nom du signet et éventuellement la valeur du`showhide` variables selon les besoins.

#### Q : Comment puis-je ajouter d'autres conditions pour afficher ou masquer le contenu des favoris ?

 R : Pour ajouter d'autres conditions, vous pouvez utiliser des opérateurs logiques tels que`AND` et`OR` dans le code d'insertion des champs de fusion à l'étape 2. Modifiez la condition dans le code suivant pour ajouter des conditions supplémentaires :

```csharp
builder. Write("\" = \"true\" ");
```

#### Q : Comment puis-je supprimer un signet dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour supprimer un signet dans un document Word à l'aide d'Aspose.Words pour .NET, vous pouvez utiliser le`Remove` méthode de la`Bookmarks` collection de la plage de documents. Voici un exemple de code pour supprimer un signet spécifique :

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Q : La bibliothèque Aspose.Words est-elle gratuite ?

 R : La bibliothèque Aspose.Words est une bibliothèque commerciale et nécessite une licence valide pour être utilisée dans vos projets. Tu peux vérifier[Aspose.Words pour les références d'API .NET](https://reference.aspose.com/words/net/) pour en savoir plus sur les options de licence et les tarifs.

#### Q : Existe-t-il d'autres bibliothèques disponibles pour le traitement de texte avec des documents Word dans .NET ?

R : Oui, il existe d'autres bibliothèques disponibles pour le traitement de texte avec des documents Word dans .NET, comme Open XML SDK et GemBox.Document. Vous pouvez explorer ces bibliothèques comme alternatives à Aspose.Words en fonction de vos besoins et préférences spécifiques.