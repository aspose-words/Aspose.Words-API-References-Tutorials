---
title: Imposta lo stile di controllo del contenuto
linktitle: Imposta lo stile di controllo del contenuto
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare lo stile di un controllo contenuto in un documento Word utilizzando Aspose.Words per .NET, applicando una formattazione coerente.
type: docs
weight: 10
url: /it/net/programming-with-sdt/set-content-control-style/
---

Questo tutorial spiega come impostare lo stile di un controllo del contenuto in un documento di Word utilizzando Aspose.Words per .NET. Puoi applicare stili predefiniti o personalizzati ai controlli del contenuto per una formattazione coerente.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e recuperare il controllo del contenuto
 Carica il documento Word usando il file`Document` costruttore, passando il percorso al documento come parametro. Recuperare il controllo del contenuto desiderato dal documento. In questo esempio, assumiamo che il controllo del contenuto sia il primo tag di documento strutturato nel documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Passaggio 3: recuperare lo stile e applicarlo al controllo del contenuto
 Recupera lo stile desiderato dalla raccolta di stili del documento. In questo esempio, recuperiamo lo stile "Quote" utilizzando`StyleIdentifier.Quote` . Quindi, assegna lo stile recuperato al file`Style` proprietà del tag del documento strutturato.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Passaggio 4: salvare il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Esempio di codice sorgente per Imposta lo stile del controllo del contenuto utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Questo è tutto! Hai impostato correttamente lo stile di un controllo del contenuto nel documento di Word utilizzando Aspose.Words per .NET.