---
title: Création d'une section répétitive de tableau mappée à une partie XML personnalisée
linktitle: Création d'une section répétitive de tableau mappée à une partie XML personnalisée
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer un tableau avec une section répétitive mappée à un CustomXmlPart dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Ce didacticiel montre comment créer un tableau avec une section répétitive mappée à une partie XML personnalisée dans un document Word à l'aide d'Aspose.Words pour .NET. La section répétitive vous permet d'ajouter dynamiquement des lignes en fonction des données XML stockées dans la partie XML personnalisée.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et DocumentBuilder
 Créez une nouvelle instance du`Document` classe et un`DocumentBuilder` pour construire le contenu du document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Ajouter des données XML personnalisées à un CustomXmlPart
 Créer un`CustomXmlPart` et ajoutez-y des données XML personnalisées. Dans cet exemple, nous créons une chaîne XML représentant une collection de livres avec leurs titres et auteurs.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Étape 4 : Créer une table et une structure de table
 Commencez à créer un tableau en utilisant le`StartTable` méthode du`DocumentBuilder` . Ajoutez des cellules et du contenu au tableau à l'aide de l'outil`InsertCell`et`Write` méthodes.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Étape 5 : Créer la section répétitive mappée sur du XML personnalisé
 Créer un`StructuredDocumentTag` avec`SdtType.RepeatingSection` pour représenter la section répétitive. Définissez le mappage XML pour la section répétitive à l'aide du`SetMapping` méthode du`XmlMapping` propriété. Dans cet exemple, nous mappons la section répétitive à`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Étape 6 : Créer l'élément de section répétitive et ajouter des cellules
 Créer un`StructuredDocumentTag` avec`SdtType.RepeatingSectionItem` pour représenter l’élément de section répétitive. Ajoutez-le en tant qu'enfant à la section répétitive.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Créer un`Row` pour représenter chaque élément de la section répétitive et l'ajouter à l'élément de la section répétitive.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Étape 7 : ajouter des contrôles de contenu dans la section répétitive
 Créer`StructuredDocumentTag` objets avec`SdtType.PlainText`

  pour représenter les contrôles de contenu du titre et de l'auteur. Définissez le mappage XML pour chaque contrôle de contenu à l'aide du`SetMapping` méthode du`XmlMapping` propriété. Dans cet exemple, nous mappons le contrôle de titre à`/books[1]/book[1]/title[1]` et le contrôle de l'auteur pour`/books[1]/book[1]/author[1]`.

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

## Étape 8 : Enregistrez le document
 Enregistrez le document modifié dans le répertoire spécifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx ».

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Exemple de code source pour la création d'une section répétitive de tableau mappée à une partie XML personnalisée à l'aide d'Aspose.Words pour .NET 

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

C'est ça! Vous avez créé avec succès un tableau avec une section répétitive mappée à un CustomXmlPart dans votre document Word à l'aide d'Aspose.Words pour .NET.