---
title: Création d'une section extensible de tableau mappée à une partie XML personnalisée
linktitle: Création d'une section extensible de tableau mappée à une partie XML personnalisée
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment créer un tableau avec une section extensible mappée à un CustomXmlPart dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Ce didacticiel montre comment créer un tableau avec une section extensible mappée à une partie Xml personnalisée dans un document Word à l'aide de Aspose.Words pour .NET. La section extensible vous permet d'ajouter dynamiquement des lignes en fonction des données XML stockées dans la partie XML personnalisée.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : créer un document et DocumentBuilder
 Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` pour construire le contenu du document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : ajouter des données XML personnalisées à un CustomXmlPart
 Créer un`CustomXmlPart` et ajoutez-y des données XML personnalisées. Dans cet exemple, nous créons une chaîne XML représentant une collection de livres avec leurs titres et leurs auteurs.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Étape 4 : créer une table et une structure de table
 Commencez à créer un tableau à l'aide de`StartTable` méthode de la`DocumentBuilder` . Ajoutez des cellules de tableau et du contenu à l'aide de la`InsertCell` et`Write` méthodes.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Étape 5 : Créer la section extensible mappée sur XML personnalisé
 Créer un`StructuredDocumentTag` avec`SdtType.RepeatingSection` pour représenter la section extensible. Définissez le mappage XML pour la section extensible à l'aide de la`SetMapping` méthode de la`XmlMapping` propriété. Dans cet exemple, nous mappons la section extensible à`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Étape 6 : créer l'élément de section extensible et ajouter des cellules
 Créer un`StructuredDocumentTag` avec`SdtType.RepeatingSectionItem` pour représenter l'élément de section extensible. Ajoutez-le en tant qu'enfant à la section extensible.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Créer un`Row`pour représenter chaque élément dans la section extensible et l'ajouter à l'élément de la section extensible.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Étape 7 : Ajouter des contrôles de contenu dans la section extensible
 Créer`StructuredDocumentTag` objets avec`SdtType.PlainText`

  pour représenter les contrôles de contenu du titre et de l'auteur. Définissez le mappage XML pour chaque contrôle de contenu à l'aide de la`SetMapping` méthode de la`XmlMapping` propriété. Dans cet exemple, nous mappons le contrôle de titre à`/books[1]/book[1]/title[1]` et le contrôle de l'auteur à`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Étape 8 : Enregistrer le document
 Enregistrez le document modifié dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Exemple de code source pour la création d'une section répétitive de tableau mappée à une partie Xml personnalisée à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

C'est ça! Vous avez créé avec succès un tableau avec une section extensible mappée à un CustomXmlPart dans votre document Word à l'aide de Aspose.Words pour .NET.