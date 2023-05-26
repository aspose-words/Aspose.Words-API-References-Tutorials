---
title: Creazione della sezione ripetuta della tabella mappata alla parte Xml personalizzata
linktitle: Creazione della sezione ripetuta della tabella mappata alla parte Xml personalizzata
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare una tabella con una sezione ripetuta mappata a una CustomXmlPart in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Questa esercitazione illustra come creare una tabella con una sezione ripetuta mappata a una parte Xml personalizzata in un documento di Word utilizzando Aspose.Words per .NET. La sezione ripetuta consente di aggiungere dinamicamente righe in base ai dati XML archiviati nella parte Xml personalizzata.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"`con il percorso effettivo della directory in cui si desidera salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` per costruire il contenuto del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: aggiungere dati XML personalizzati a CustomXmlPart
 Creare un`CustomXmlPart` e aggiungervi dati XML personalizzati. In questo esempio, creiamo una stringa XML che rappresenta una raccolta di libri con i loro titoli e autori.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Passaggio 4: creare una tabella e una struttura della tabella
 Inizia a creare una tabella utilizzando il file`StartTable` metodo del`DocumentBuilder` . Aggiungi celle e contenuto della tabella utilizzando il file`InsertCell` E`Write` metodi.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Passaggio 5: creare la sezione ripetuta mappata su XML personalizzato
 Creare un`StructuredDocumentTag` con`SdtType.RepeatingSection` per rappresentare la sezione ripetuta. Impostare la mappatura XML per la sezione ripetuta utilizzando il file`SetMapping` metodo del`XmlMapping` proprietà. In questo esempio, mappiamo la sezione ripetuta a`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Passaggio 6: creare l'elemento della sezione ripetuta e aggiungere celle
 Creare un`StructuredDocumentTag` con`SdtType.RepeatingSectionItem` per rappresentare l'elemento della sezione ripetuta. Aggiungilo come bambino alla sezione ripetuta.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Creare un`Row`per rappresentare ogni elemento nella sezione ripetuta e aggiungerlo all'elemento della sezione ripetuta.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Passaggio 7: aggiungi i controlli del contenuto all'interno della sezione ripetuta
 Creare`StructuredDocumentTag` oggetti con`SdtType.PlainText`

  per rappresentare il titolo e i controlli del contenuto dell'autore. Impostare la mappatura XML per ogni controllo del contenuto utilizzando il file`SetMapping` metodo del`XmlMapping` proprietà. In questo esempio, mappiamo il controllo del titolo a`/books[1]/book[1]/title[1]` e il controllo dell'autore a`/books[1]/book[1]/author[1]`.

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

## Passaggio 8: salvare il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Esempio di codice sorgente per la creazione di una sezione ripetuta della tabella mappata alla parte Xml personalizzata utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
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

Questo è tutto! Hai creato correttamente una tabella con una sezione ripetuta mappata a una CustomXmlPart nel documento di Word utilizzando Aspose.Words per .NET.