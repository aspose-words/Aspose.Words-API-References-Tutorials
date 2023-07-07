---
title: Effacer le contrôle du contenu
linktitle: Effacer le contrôle du contenu
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à effacer le contenu d'un contrôle dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/clear-contents-control/
---

Ce didacticiel montre comment effacer le contenu d'un SDT dans un document Word à l'aide de Aspose.Words pour .NET. L'effacement du contenu d'un SDT supprime tout texte ou nœud enfant dans le contrôle de contenu.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel au répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document et obtenir le StructuredDocumentTag
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en tant que paramètre. Ensuite, récupérez le`StructuredDocumentTag` à partir du document. Dans cet exemple, nous supposons que le SDT est le premier nœud enfant du document.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Étape 3 : Effacer le contenu du StructuredDocumentTag
 Effacez le contenu du SDT à l'aide de la`Clear` méthode. Cela supprime tout texte ou nœud enfant dans le contrôle de contenu.

```csharp
sdt.Clear();
```

## Étape 4 : Enregistrer le document
Enregistrez le document modifié à l'aide de la`Save`méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Exemple de code source pour Clear Contents Control à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

C'est ça! Vous avez réussi à effacer le contenu d'un StructuredDocumentTag dans votre document Word à l'aide de Aspose.Words pour .NET.