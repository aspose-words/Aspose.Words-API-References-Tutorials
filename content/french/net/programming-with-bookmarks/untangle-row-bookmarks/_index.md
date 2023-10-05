---
title: Démêler les signets de ligne dans un document Word
linktitle: Démêler les signets de ligne dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment démêler les signets de lignes imbriquées dans un document Word pour supprimer des lignes spécifiques sans affecter les autres signets.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/untangle-row-bookmarks/
---

Dans cet article, nous explorerons le code source C# ci-dessus pour comprendre comment utiliser la fonction Untangle Row Bookmarks dans la bibliothèque Aspose.Words pour .NET. Cette fonction permet de mettre les fins de marque-pages de lignes sur la même ligne que les débuts de marque-pages.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Chargement du document

 Nous utilisons le`Document` classe pour charger le document existant à partir d'un fichier :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Étape 2 : Démêler les signets de ligne

 Nous utilisons le`Untangle` fonction pour démêler les signets des lignes. Cette fonction effectue la tâche personnalisée consistant à placer les fins de lignes du signet sur la même ligne que le début du signet :

```csharp
Untangle(doc);
```

## Étape 3 : Supprimer la ligne par signet

 Nous utilisons le`DeleteRowByBookmark` fonction pour supprimer une ligne spécifique par son signet :

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Étape 4 : Vérifiez l'intégrité des autres signets

On vérifie que les autres marque-pages n'ont pas été endommagés en vérifiant si la fin du marque-page est toujours présente :

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Exemple de code source pour les signets de ligne Untangle à l'aide d'Aspose.Words pour .NET

Voici l’exemple complet de code source pour démêler les signets des lignes à l’aide d’Aspose.Words for .NET :


```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Cela effectue la tâche personnalisée consistant à placer les fins de signet de ligne dans la même ligne que le début du signet.
	Untangle(doc);

	// Nous pouvons désormais facilement supprimer des lignes d'un signet sans endommager les signets d'une autre ligne.
	DeleteRowByBookmark(doc, "ROW2");

	// Il s'agit simplement de vérifier que l'autre marque-page n'a pas été endommagé.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Démêler le code source
```csharp

private void Untangle(Document doc)
        {
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
        }

```

#### Code source de SupprimerRowByBookmark
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité Untangle Row Bookmarks d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour démêler les signets de ligne et supprimer une ligne spécifique sans endommager les autres signets.

### FAQ pour démêler les signets de lignes dans un document Word

#### Q : Unscramble Row Bookmarks fonctionne-t-il uniquement avec les signets de lignes dans les tableaux ?

R : Oui, la fonctionnalité Démêler les signets de lignes est spécialement conçue pour démêler les signets de lignes qui se trouvent dans les tableaux. Cette fonction peut être utilisée pour traiter les signets de ligne dans des tableaux et garantir que les fins de signet sont sur la même ligne que le début du signet.

#### Q : La fonction Déchiffrer les signets de ligne modifie-t-elle le contenu du document original ?

R : Oui, la fonction Déchiffrer les signets de ligne modifie le document original en déplaçant les extrémités des signets de ligne pour les placer sur la même ligne que les débuts des signets. Assurez-vous d'enregistrer une copie de sauvegarde du document avant d'appliquer cette fonctionnalité.

#### Q : Comment puis-je identifier les signets de ligne dans mon document Word ?

R : Les signets de lignes sont généralement utilisés dans les tableaux pour marquer des sections spécifiques. Vous pouvez identifier les signets de lignes en parcourant les signets dans le document et en vérifiant si les signets se trouvent dans les lignes du tableau.

#### Q : Est-il possible de démêler les signets de lignes dans les tableaux non adjacents ?

R : La fonction Démêler les signets de lignes présentée dans cet article est conçue pour démêler les signets de lignes dans les tableaux adjacents. Pour démêler les signets de lignes dans les tableaux non adjacents, des ajustements supplémentaires du code peuvent être nécessaires en fonction de la structure du document.

#### Q : Quelles autres manipulations puis-je effectuer sur les signets de lignes une fois qu'ils ont été démêlés ?

R : Une fois les marque-pages défaits, vous pouvez effectuer différentes manipulations selon vos besoins. Cela peut inclure la modification, la suppression ou l’ajout de contenu aux lignes mises en signet. Assurez-vous de manipuler les signets de ligne avec soin pour éviter tout impact indésirable sur le reste du document.