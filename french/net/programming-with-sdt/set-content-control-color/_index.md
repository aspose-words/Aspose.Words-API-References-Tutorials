---
title: Définir la couleur du contrôle du contenu
linktitle: Définir la couleur du contrôle du contenu
second_title: API de traitement de documents Aspose.Words
description: Apprenez à définir la couleur d'un contrôle de contenu dans un document Word à l'aide d'Aspose.Words pour .NET, en personnalisant son apparence.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/set-content-control-color/
---

Ce didacticiel explique comment définir la couleur d'un contrôle de contenu dans un document Word à l'aide de Aspose.Words pour .NET. Vous pouvez personnaliser l'apparence des contrôles de contenu en modifiant leur couleur.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de texte avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel au répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : chargez le document et récupérez le contrôle de contenu
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en tant que paramètre. Récupérez le contrôle de contenu souhaité dans le document. Dans cet exemple, nous supposons que le contrôle de contenu est la première balise de document structuré du document.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Étape 3 : Définir la couleur du contrôle du contenu
 Définissez la couleur du contrôle de contenu en attribuant un`Color` valeur à la`Color` propriété de la balise de document structuré. Dans cet exemple, nous définissons la couleur sur le rouge.

```csharp
sdt.Color = Color.Red;
```

## Étape 4 : Enregistrer le document
 Enregistrez le document modifié dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Exemple de code source pour Set Content Control Color à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

C'est ça! Vous avez défini avec succès la couleur d'un contrôle de contenu dans votre document Word à l'aide de Aspose.Words pour .NET.