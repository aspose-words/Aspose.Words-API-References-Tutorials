---
title: Lier SDT à une partie XML personnalisée
linktitle: Lier SDT à une partie XML personnalisée
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment lier un SDT à une partie XML personnalisée à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Ce didacticiel montre comment lier une balise de document structuré (SDT) à une partie XML personnalisée à l'aide d'Aspose.Words pour .NET. Les SDT vous permettent d'ajouter des contrôles de contenu structuré à un document Word, et CustomXmlParts fournit un moyen de stocker des données XML personnalisées associées au document.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et XML.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et CustomXmlPart
 Créez une nouvelle instance du`Document` classe et un`CustomXmlPart` pour stocker les données XML personnalisées. Le XML personnalisé doit être dans un format XML valide. Dans cet exemple, nous utilisons une simple chaîne XML`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Étape 3 : ajouter un StructuredDocumentTag (SDT) au document
 Ajouter un`StructuredDocumentTag`au document pour servir de contrôle de contenu. Spécifie le`SdtType` comme`PlainText` et le`MarkupLevel` comme`Block` pour créer un SDT au niveau du bloc.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Étape 4 : Définir le mappage XML pour le SDT
 Mappez le SDT sur le`CustomXmlPart` en utilisant le`SetMapping` méthode du`XmlMapping` propriété. Spécifie le`CustomXmlPart` , l'expression XPath pour localiser le nœud XML souhaité et le préfixe de l'espace de noms si nécessaire. Dans cet exemple, nous mappons le SDT à`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Étape 5 : Enregistrez le document
 Enregistrez le document modifié dans le répertoire spécifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithSdt.BindSDTtoCustomXmlPart.doc ».

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Exemple de code source pour Bind Sd Tto Custom Xml Part à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

C'est ça! Vous avez lié avec succès un SDT à un CustomXmlPart dans votre document Word à l'aide d'Aspose.Words pour .NET.