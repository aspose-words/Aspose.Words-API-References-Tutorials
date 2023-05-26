---
title: Intervallo tag documento strutturato Avvia mappatura Xml
linktitle: Intervallo tag documento strutturato Avvia mappatura Xml
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare la mappatura XML per un intervallo di tag di documenti strutturati inizia in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Questo tutorial spiega come impostare la mappatura XML per un intervallo di tag di documento strutturato in un documento di Word utilizzando Aspose.Words per .NET. Il mapping XML consente di visualizzare parti specifiche di un'origine dati XML all'interno del controllo contenuto.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e creare la parte XML
 Carica il documento Word usando il file`Document` costruttore, passando il percorso al documento come parametro. Creare una parte XML che contenga i dati che si desidera visualizzare all'interno del tag del documento strutturato.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Passaggio 3: impostare la mappatura XML per il tag del documento strutturato
Recupera l'intervallo di tag del documento strutturato a partire dal documento. Quindi, imposta la mappatura XML per il tag del documento strutturato in modo da visualizzare una parte specifica della parte XML personalizzata utilizzando un'espressione XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Passaggio 4: salvare il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Esempio di codice sorgente per l'intervallo di tag del documento strutturato Avviare la mappatura Xml utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
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
	// visualizzerà solo una parte della CustomXmlPart a cui punta l'XPath.
	// Questo XPath punterà al contenuto del secondo elemento "<text>" del primo elemento "<root>" della nostra CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Questo è tutto! Hai impostato correttamente la mappatura XML per un inizio di intervallo di tag di documento strutturato nel documento di Word utilizzando Aspose.Words per .NET.