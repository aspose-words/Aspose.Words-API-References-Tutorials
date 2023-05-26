---
title: Démêler les signets de ligne
linktitle: Démêler les signets de ligne
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment démêler les signets de ligne imbriqués pour supprimer des lignes spécifiques sans affecter les autres signets.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/untangle-row-bookmarks/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Untangle Row Bookmarks dans la bibliothèque Aspose.Words pour .NET. Cette fonction permet de mettre les fins de signets de lignes sur la même ligne que les débuts de signets.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Chargement du document

 Nous utilisons le`Document` class pour charger le document existant à partir d'un fichier :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Étape 2 : démêler les signets de ligne

 Nous utilisons le`Untangle` fonction pour démêler les signets des lignes. Cette fonction exécute la tâche personnalisée consistant à placer les fins de ligne du signet sur la même ligne que le début du signet :

```csharp
Untangle(doc);
```

## Étape 3 : Supprimer la ligne par signet

 Nous utilisons le`DeleteRowByBookmark` fonction pour supprimer une ligne spécifique par son signet :

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Étape 4 : Vérifier l'intégrité des autres signets

Nous vérifions que les autres signets n'ont pas été endommagés en vérifiant si la fin du signet est toujours présente :

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Exemple de code source pour démêler les signets de lignes à l'aide de Aspose.Words pour .NET**

Voici l'exemple de code source complet pour démêler les signets des lignes à l'aide d'Aspose.Words pour .NET :


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Cela exécute la tâche personnalisée consistant à placer les extrémités du signet de ligne dans la même ligne avec le début du signet.
	Untangle(doc);

	// Maintenant, nous pouvons facilement supprimer des lignes par un signet sans endommager les signets d'une autre ligne.
	DeleteRowByBookmark(doc, "ROW2");

	// C'est juste pour vérifier que l'autre signet n'a pas été endommagé.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité Untangle Row Bookmarks d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour démêler les signets de ligne et supprimer une ligne spécifique sans endommager les autres signets.