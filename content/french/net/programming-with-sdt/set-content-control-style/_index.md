---
title: Définir le style de contrôle du contenu
linktitle: Définir le style de contrôle du contenu
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir le style d'un contrôle de contenu dans un document Word à l'aide d'Aspose.Words for .NET, en appliquant une mise en forme cohérente.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/set-content-control-style/
---

Ce didacticiel explique comment définir le style d'un contrôle de contenu dans un document Word à l'aide d'Aspose.Words pour .NET. Vous pouvez appliquer des styles prédéfinis ou personnalisés aux contrôles de contenu pour une mise en forme cohérente.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers le répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : charger le document et récupérer le contrôle de contenu
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en paramètre. Récupérez le contrôle de contenu souhaité à partir du document. Dans cet exemple, nous supposons que le contrôle de contenu est la première balise de document structuré du document.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Étape 3 : récupérer le style et l'appliquer au contrôle de contenu
 Récupérez le style souhaité dans la collection de styles du document. Dans cet exemple, nous récupérons le style "Quote" en utilisant`StyleIdentifier.Quote` . Ensuite, attribuez le style récupéré au`Style` propriété de la balise du document structuré.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Étape 4 : Enregistrez le document
 Enregistrez le document modifié dans le répertoire spécifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithSdt.SetContentControlStyle.docx ».

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Exemple de code source pour définir le style de contrôle de contenu à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

C'est ça! Vous avez réussi à définir le style d'un contrôle de contenu dans votre document Word à l'aide d'Aspose.Words pour .NET.