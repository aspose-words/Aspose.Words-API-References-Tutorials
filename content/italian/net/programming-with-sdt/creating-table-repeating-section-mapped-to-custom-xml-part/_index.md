---
title: Creazione di una sezione ripetuta di tabella mappata su una parte Xml personalizzata
linktitle: Creazione di una sezione ripetuta di tabella mappata su una parte Xml personalizzata
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare una tabella con una sezione ripetuta mappata su CustomXmlPart in un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Questo tutorial dimostra come creare una tabella con una sezione ripetuta mappata su una parte Xml personalizzata in un documento Word utilizzando Aspose.Words per .NET. La sezione ripetuta consente di aggiungere dinamicamente righe in base ai dati XML archiviati nella parte XML personalizzata.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui desideri salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` per costruire il contenuto del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: aggiungere dati XML personalizzati a CustomXmlPart
 Creare un`CustomXmlPart` e aggiungivi dati XML personalizzati. In questo esempio creiamo una stringa XML che rappresenta una raccolta di libri con i relativi titoli e autori.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Passaggio 4: crea una tabella e una struttura di tabella
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

## Passaggio 5: crea la sezione ripetuta mappata su XML personalizzato
 Creare un`StructuredDocumentTag` con`SdtType.RepeatingSection` per rappresentare la sezione ripetuta. Imposta la mappatura XML per la sezione ripetuta utilizzando il comando`SetMapping` metodo del`XmlMapping` proprietà. In questo esempio, mappiamo la sezione ripetuta a`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Passaggio 6: crea l'elemento di sezione ripetuto e aggiungi celle
 Creare un`StructuredDocumentTag` con`SdtType.RepeatingSectionItem` per rappresentare l'elemento della sezione ripetuto. Aggiungilo come figlio alla sezione ripetuta.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Creare un`Row`per rappresentare ciascun elemento nella sezione ripetuta e aggiungerlo all'elemento della sezione ripetuta.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Passaggio 7: aggiungi i controlli del contenuto nella sezione ripetuta
 Creare`StructuredDocumentTag` oggetti con`SdtType.PlainText`

  per rappresentare i controlli del contenuto del titolo e dell'autore. Imposta la mappatura XML per ogni controllo del contenuto utilizzando il file`SetMapping` metodo del`XmlMapping` proprietà. In questo esempio, mappiamo il controllo del titolo su`/books[1]/book[1]/title[1]` e il controllo dell'autore su`/books[1]/book[1]/author[1]`.

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

## Passaggio 8: salva il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Codice sorgente di esempio per la creazione di sezioni ripetute di tabella mappate su parti Xml personalizzate utilizzando Aspose.Words per .NET 

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

Questo è tutto! Hai creato con successo una tabella con una sezione ripetuta mappata su CustomXmlPart nel tuo documento Word utilizzando Aspose.Words per .NET.