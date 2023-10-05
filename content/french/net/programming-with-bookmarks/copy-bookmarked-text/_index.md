---
title: Copier le texte marqué dans un document Word
linktitle: Copier le texte marqué dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment copier le texte d'un signet d'un document Word vers un autre document à l'aide d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/copy-bookmarked-text/
---

Dans cet article, nous explorerons le code source C# ci-dessus pour comprendre comment utiliser la fonction Copier le texte marqué dans les favoris dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet de copier le contenu d'un signet spécifique d'un document source vers un autre document.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Chargement du document source

 Avant de copier le texte du signet, nous devons charger le document source dans un`Document` objet en utilisant le chemin du fichier :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Étape 2 : Obtenir le signet source

 Nous utilisons le`Bookmarks` propriété de la plage du document source pour obtenir le signet spécifique que nous voulons copier :

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Étape 3 : Création du document de destination

Nous créons un nouveau document qui servira de document de destination pour copier le contenu du signet :

```csharp
Document dstDoc = new Document();
```

## Étape 4 : Spécification de l'emplacement de copie

Nous spécifions l'emplacement où nous voulons ajouter le texte copié. Dans notre exemple, nous ajoutons le texte à la fin du corps de la dernière section du document de destination :

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Étape 5 : Importer et copier le texte du signet

 Nous utilisons un`NodeImporter`objet pour importer et copier le texte du signet d'un document source vers le document de destination :

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Exemple de code source pour copier du texte marqué à l'aide d'Aspose.Words pour .NET

Voici l'exemple complet de code source pour illustrer la copie de texte à partir d'un signet à l'aide d'Aspose.Words for .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Il s'agit du signet dont nous voulons copier le contenu.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Nous compléterons ce document.
	Document dstDoc = new Document();

	// Disons que nous serons ajoutés à la fin du corps de la dernière section.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Si vous importez plusieurs fois sans un seul contexte, de nombreux styles seront créés.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AppendBookmarkedText Code source

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
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
                //Cela crée une copie du nœud actuel et l'importe (le rend valide) dans le contexte
                // du document de destination. Importer signifie ajuster correctement les styles et les identifiants de liste.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Copier le texte mis en signet à partir d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour copier le contenu d'un signet d'un document source vers un autre document.

### FAQ pour copier du texte mis en signet dans un document Word

#### Q : Quelles sont les conditions requises pour utiliser la fonctionnalité « Copier le texte avec les favoris » dans Aspose.Words pour .NET ?

R : Pour utiliser la fonctionnalité « Copier du texte avec des signets » dans Aspose.Words for .NET, vous devez avoir des connaissances de base du langage C#. Vous avez également besoin d'un environnement de développement .NET avec la bibliothèque Aspose.Words installée.

#### Q : Comment charger un document source dans Aspose.Words pour .NET ?

 R : Pour charger un document source dans Aspose.Words for .NET, vous pouvez utiliser le`Document` classe en spécifiant le chemin du fichier du document. Voici un exemple de code :

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Q : Comment obtenir le contenu d'un signet spécifique dans un document source à l'aide d'Aspose.Words pour .NET ?

 R : Pour obtenir le contenu d'un signet spécifique dans un document source à l'aide d'Aspose.Words for .NET, vous pouvez accéder au`Bookmarks` propriété de la plage du document source et utilisez le nom du signet pour récupérer le signet spécifique. Voici un exemple de code :

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Q : Comment spécifier l'emplacement de la copie du texte du signet dans un document de destination à l'aide d'Aspose.Words pour .NET ?

 R : Pour spécifier où vous souhaitez ajouter le texte de signet copié dans un document de destination à l'aide d'Aspose.Words for .NET, vous pouvez accéder au corps de la dernière section du document de destination. Vous pouvez utiliser le`LastSection` propriété pour accéder à la dernière section et à la`Body` propriété pour accéder au corps de cette section. Voici un exemple de code :

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Q : Comment importer et copier le texte d'un signet du document source vers le document de destination à l'aide d'Aspose.Words pour .NET ?

 R : Pour importer et copier le texte d'un signet d'un document source vers un document de destination à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`NodeImporter` classe spécifiant le document source, le document de destination et le mode de formatage à conserver. Ensuite, vous pouvez utiliser le`AppendBookmarkedText` méthode pour ajouter le texte du signet dans le document de destination. Voici un exemple de code :

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Q : Comment enregistrer un document de destination après avoir copié le texte du signet à l'aide d'Aspose.Words pour .NET ?

R : Pour enregistrer un document de destination après avoir copié le texte d'un signet à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`Save` méthode du`Document` objet spécifiant le chemin du fichier de destination. Voici un exemple de code :

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```