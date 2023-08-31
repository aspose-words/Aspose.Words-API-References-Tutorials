---
title: Intervallo tag documento strutturato Avvia la mappatura Xml
linktitle: Intervallo tag documento strutturato Avvia la mappatura Xml
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare la mappatura XML per un intervallo di tag di documento strutturato che inizia in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Questo tutorial spiega come impostare la mappatura XML per un intervallo di tag di documento strutturato che inizia in un documento di Word utilizzando Aspose.Words per .NET. La mappatura XML consente di visualizzare parti specifiche di un'origine dati XML all'interno del controllo del contenuto.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e creare la parte XML
 Caricare il documento Word utilizzando il file`Document` costruttore, passando il percorso del documento come parametro. Crea una parte XML che contenga i dati che desideri visualizzare all'interno del tag del documento strutturato.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Passaggio 3: imposta la mappatura XML per il tag del documento strutturato
Recupera l'intervallo di tag del documento strutturato a partire dal documento. Quindi, imposta la mappatura XML per il tag del documento strutturato per visualizzare una parte specifica della parte XML personalizzata utilizzando un'espressione XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Passaggio 4: salva il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Codice sorgente di esempio per l'intervallo di tag del documento strutturato Avvia la mappatura Xml utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Costruisci una parte XML che contiene dati e aggiungila alla raccolta CustomXmlPart del documento.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Crea un StructuredDocumentTag che visualizzerà il contenuto della nostra CustomXmlPart nel documento.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Se impostiamo una mappatura per il nostro StructuredDocumentTag,
	// visualizzerà solo una parte di CustomXmlPart a cui punta XPath.
	// Questo XPath punterà al contenuto del secondo elemento "<text>" del primo elemento "<root>" della nostra CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Questo è tutto! Hai impostato correttamente la mappatura XML per un intervallo di tag di documento strutturato che inizia nel tuo documento Word utilizzando Aspose.Words per .NET.