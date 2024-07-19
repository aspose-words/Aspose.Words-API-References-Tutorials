---
title: Effacer le contrôle du contenu
linktitle: Effacer le contrôle du contenu
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment effacer le contenu d'un contrôle dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/clear-contents-control/
---

Ce didacticiel montre comment effacer le contenu d'un SDT dans un document Word à l'aide d'Aspose.Words pour .NET. Effacer le contenu d'un SDT supprime tout texte ou nœuds enfants dans le contrôle de contenu.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers le répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le document et obtenez le StructuredDocumentTag
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en paramètre. Ensuite, récupérez le fichier souhaité`StructuredDocumentTag`du document. Dans cet exemple, nous supposons que le SDT est le premier nœud enfant du document.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Étape 3 : Effacer le contenu du StructuredDocumentTag
 Effacez le contenu du SDT à l'aide du`Clear` méthode. Cela supprime tout texte ou nœuds enfants dans le contrôle de contenu.

```csharp
sdt.Clear();
```

## Étape 4 : Enregistrez le document
 Enregistrez le document modifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithSdt.ClearContentsControl.doc ».

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Exemple de code source pour Clear Contents Control à l’aide d’Aspose.Words for .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

C'est ça! Vous avez effacé avec succès le contenu d’un StructuredDocumentTag dans votre document Word à l’aide d’Aspose.Words pour .NET.