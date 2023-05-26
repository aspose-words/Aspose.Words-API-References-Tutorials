---
title: Accéder aux signets
linktitle: Accéder aux signets
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment accéder aux signets dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/access-bookmarks/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Access Bookmarks dans Aspose.Words pour la bibliothèque .NET. Cette fonctionnalité permet d'accéder à des signets spécifiques dans un document Word.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Chargement du document

 Avant de commencer à accéder aux signets, nous devons charger un document Word à l'aide de Aspose.Words pour .NET. Cela peut être fait en instanciant un`Document` objet spécifiant le chemin du fichier du document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Étape 2 : Accéder aux signets

Une fois le document chargé, nous pouvons accéder aux signets du document. Il existe deux manières d'accéder aux signets : par index et par nom.

- Accès par index : Dans notre exemple, nous utilisons l'index 0 pour accéder au premier signet du document :

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Accès par nom : Dans notre exemple, nous utilisons le nom "MonSignet3" pour accéder à un signet spécifique dans le document :

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Exemple de code source pour Access Bookmarks utilisant Aspose.Words pour .NET

Voici l'exemple de code source complet pour démontrer l'accès aux signets à l'aide d'Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Par indice :
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// De nom:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité Access Bookmarks d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour télécharger un document et accéder aux signets en utilisant l'index et le nom.