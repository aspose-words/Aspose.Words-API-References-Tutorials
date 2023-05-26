---
title: Définir le style de contrôle du contenu
linktitle: Définir le style de contrôle du contenu
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à définir le style d'un contrôle de contenu dans un document Word à l'aide d'Aspose.Words pour .NET, en appliquant une mise en forme cohérente.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/set-content-control-style/
---

Ce didacticiel explique comment définir le style d'un contrôle de contenu dans un document Word à l'aide de Aspose.Words pour .NET. Vous pouvez appliquer des styles prédéfinis ou personnalisés aux contrôles de contenu pour une mise en forme cohérente.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

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

## Étape 3 : Récupérer le style et l'appliquer au contrôle de contenu
 Récupérez le style souhaité dans la collection de styles du document. Dans cet exemple, on récupère le style "Quote" en utilisant`StyleIdentifier.Quote` . Ensuite, affectez le style récupéré au`Style` propriété de la balise de document structuré.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Étape 4 : Enregistrer le document
 Enregistrez le document modifié dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Exemple de code source pour Définir le style de contrôle du contenu à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

C'est ça! Vous avez défini avec succès le style d'un contrôle de contenu dans votre document Word à l'aide de Aspose.Words pour .NET.