---
title: Plage de balises de document structuré Démarrer le mappage XML
linktitle: Plage de balises de document structuré Démarrer le mappage XML
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment configurer le mappage XML pour une plage de balises de document structuré commençant dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Ce didacticiel explique comment configurer le mappage XML pour une plage de balises de document structuré commençant dans un document Word à l'aide d'Aspose.Words pour .NET. Le mappage XML vous permet d'afficher des parties spécifiques d'une source de données XML dans le contrôle de contenu.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers le répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : charger le document et créer une partie XML
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en paramètre. Créez une partie XML contenant les données que vous souhaitez afficher dans la balise du document structuré.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Étape 3 : Définir le mappage XML pour la balise de document structuré
Récupérez le début de la plage de balises du document structuré à partir du document. Ensuite, définissez le mappage XML pour la balise du document structuré afin d'afficher une partie spécifique de la partie XML personnalisée à l'aide d'une expression XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Étape 4 : Enregistrez le document
 Enregistrez le document modifié dans le répertoire spécifié à l'aide du`Save`méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx ».

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Exemple de code source pour la plage de balises de document structuré Démarrer le mappage XML à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Construisez une partie XML contenant des données et ajoutez-la à la collection CustomXmlPart du document.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Créez un StructuredDocumentTag qui affichera le contenu de notre CustomXmlPart dans le document.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Si nous définissons un mappage pour notre StructuredDocumentTag,
	// il n'affichera qu'une partie du CustomXmlPart vers laquelle pointe XPath.
	// Ce XPath pointera vers le contenu du deuxième élément "<text>" du premier élément "<root>" de notre CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

C'est ça! Vous avez configuré avec succès le mappage XML pour le début d’une plage de balises de document structuré dans votre document Word à l’aide d’Aspose.Words pour .NET.