---
title: Afficher Masquer les signets dans un document Word
linktitle: Afficher Masquer les signets dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment afficher ou masquer un signet spécifique dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/show-hide-bookmarks/
---

Dans cet article, nous explorerons le code source C# ci-dessus pour comprendre comment utiliser la fonction Afficher les signets masqués dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet d'afficher ou de masquer un signet spécifique dans un document Word.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Chargement du document

 Nous utilisons le`Document` classe pour charger le document existant à partir d'un fichier :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Étape 2 : Afficher ou masquer un favori spécifique

 Nous utilisons le`ShowHideBookmarkedContent` fonction pour afficher ou masquer un signet spécifique dans le document. Cette fonction prend en paramètres le document, le nom du signet et un booléen pour indiquer s'il faut afficher ou masquer le signet :

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Étape 3 : Sauvegarde du document modifié

 Nous utilisons le`Save` méthode pour enregistrer le document modifié dans un fichier :

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Exemple de code source pour Afficher Masquer les signets à l'aide d'Aspose.Words pour .NET

Voici l'exemple complet de code source pour démontrer l'affichage ou le masquage d'un signet spécifique à l'aide d'Aspose.Words pour .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### Afficher le code source de ShowHideBookmarkedContent

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MERGEFIELD bookmark}" = "true" "" ""}
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
        }
		
```
## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité Afficher les signets masqués d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour afficher ou masquer un signet spécifique dans un document.

### FAQ pour afficher les signets masqués dans un document Word

#### Q : Puis-je afficher ou masquer plusieurs signets dans le même document ?

R : Oui, vous pouvez afficher ou masquer plusieurs signets dans le même document en répétant les étapes 2 et 3 pour chaque signet que vous souhaitez traiter.

#### Q : Le code fourni fonctionne-t-il avec d'autres formats de documents Word, tels que .doc ou .docm ?

: Oui, le code fourni fonctionne avec différents formats de documents Word pris en charge par Aspose.Words, tels que .doc et .docm. Assurez-vous simplement d'utiliser le nom de fichier et le chemin corrects lors du chargement et de l'enregistrement du document.

#### Q : Comment puis-je afficher à nouveau un favori masqué ?

 R : Pour afficher à nouveau un signet masqué, vous devez utiliser le même`ShowHideBookmarkedContent` fonction passant la valeur`true` pour le paramètre booléen qui indique s'il faut afficher ou masquer le signet.

#### Q : Puis-je utiliser des conditions pour afficher ou masquer les signets en fonction des valeurs des champs de fusion dans le document ?

 R : Oui, vous pouvez utiliser des conditions et fusionner les valeurs des champs pour déterminer si un signet doit être affiché ou masqué. Vous pouvez personnaliser le code du`ShowHideBookmarkedContent` fonction pour prendre en compte les conditions et les valeurs appropriées.

#### Q : Comment puis-je supprimer un signet dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour supprimer un signet dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`RemoveBookmarks` méthode du`Document` classe. Voici un exemple de code :

```csharp
doc.RemoveBookmarks("BookmarkName");
```