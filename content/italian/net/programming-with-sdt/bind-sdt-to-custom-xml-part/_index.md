---
title: Associa SDT alla parte Xml personalizzata
linktitle: Associa SDT alla parte Xml personalizzata
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come associare un SDT a una parte Xml personalizzata utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Questo tutorial dimostra come associare un tag di documento strutturato (SDT) a una parte Xml personalizzata utilizzando Aspose.Words per .NET. Gli SDT consentono di aggiungere controlli del contenuto strutturato a un documento Word e CustomXmlParts fornisce un modo per archiviare dati XML personalizzati associati al documento.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# e XML.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui desideri salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un documento e CustomXmlPart
 Crea una nuova istanza di`Document` classe e a`CustomXmlPart` per memorizzare i dati XML personalizzati. L'XML personalizzato deve essere in un formato XML valido. In questo esempio utilizziamo una semplice stringa XML`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Passaggio 3: aggiungere uno StructuredDocumentTag (SDT) al documento
 Aggiungere un`StructuredDocumentTag` al documento per fungere da controllo del contenuto. Specificare la`SdtType` COME`PlainText` e il`MarkupLevel` COME`Block` per creare un SDT a livello di blocco.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Passaggio 4: impostare la mappatura XML per l'SDT
 Mappare l'SDT al file`CustomXmlPart` utilizzando il`SetMapping` metodo del`XmlMapping` proprietà. Specificare la`CustomXmlPart` , l'espressione XPath per individuare il nodo XML desiderato e il prefisso dello spazio dei nomi, se necessario. In questo esempio, mappiamo l'SDT a`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Passaggio 5: salva il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Codice sorgente di esempio per Bind Sd Tto Custom Xml Part utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Questo è tutto! Hai associato con successo un SDT a un CustomXmlPart nel tuo documento Word utilizzando Aspose.Words per .NET.