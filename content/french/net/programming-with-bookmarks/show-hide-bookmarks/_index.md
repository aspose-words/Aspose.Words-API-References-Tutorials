---
title: Afficher les signets masqués dans le document Word
linktitle: Afficher les signets masqués dans le document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à afficher ou à masquer un signet spécifique dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/show-hide-bookmarks/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Afficher les signets masqués dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet d'afficher ou de masquer un signet spécifique dans un document Word.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Chargement du document

 Nous utilisons le`Document` class pour charger le document existant à partir d'un fichier :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Étape 2 : Afficher ou masquer un signet spécifique

 Nous utilisons le`ShowHideBookmarkedContent` fonction pour afficher ou masquer un signet spécifique dans le document. Cette fonction prend en paramètre le document, le nom du signet et un booléen pour indiquer s'il faut afficher ou masquer le signet :

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Étape 3 : Enregistrer le document modifié

 Nous utilisons le`Save` méthode pour enregistrer le document modifié dans un fichier :

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Exemple de code source pour Afficher les signets masqués à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour démontrer l'affichage ou le masquage d'un signet spécifique à l'aide de Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité Afficher les signets masqués d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour afficher ou masquer un signet spécifique dans un document.

### FAQ pour afficher les signets masqués dans un document Word

#### Q : Puis-je afficher ou masquer plusieurs signets dans le même document ?

R : Oui, vous pouvez afficher ou masquer plusieurs signets dans le même document en répétant les étapes 2 et 3 pour chaque signet que vous souhaitez traiter.

#### Q : Le code fourni fonctionne-t-il avec d'autres formats de document Word, tels que .doc ou .docm ?

R : Oui, le code fourni fonctionne avec divers formats de document Word pris en charge par Aspose.Words, tels que .doc et .docm. Assurez-vous simplement d'utiliser le nom de fichier et le chemin d'accès corrects lors du chargement et de l'enregistrement du document.

#### Q : Comment puis-je afficher à nouveau un signet masqué ?

 R : Pour afficher à nouveau un signet masqué, vous devez utiliser le même`ShowHideBookmarkedContent` fonction passant la valeur`true`pour le paramètre booléen qui indique s'il faut afficher ou masquer le signet.

#### Q : Puis-je utiliser des conditions pour afficher ou masquer des signets en fonction des valeurs de champ de fusion dans le document ?

 R : Oui, vous pouvez utiliser des conditions et des valeurs de champ de fusion pour déterminer si un signet doit être affiché ou masqué. Vous pouvez personnaliser le code du`ShowHideBookmarkedContent` fonction pour prendre en compte les conditions et les valeurs appropriées.

#### Q : Comment puis-je supprimer un signet dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour supprimer un signet dans un document Word à l'aide d'Aspose.Words pour .NET, vous pouvez utiliser le`RemoveBookmarks` méthode de la`Document`classe. Voici un exemple de code :

```csharp
doc.RemoveBookmarks("BookmarkName");
```