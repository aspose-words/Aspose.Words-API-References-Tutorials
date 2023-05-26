---
title: Controllo del contenuto del tipo di casella di controllo
linktitle: Controllo del contenuto del tipo di casella di controllo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare un controllo del contenuto del tipo di casella di controllo in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/check-box-type-content-control/
---

Questo tutorial spiega come creare un controllo del contenuto del tipo di casella di controllo in un documento di Word utilizzando Aspose.Words per .NET. I controlli del contenuto della casella di controllo consentono agli utenti di selezionare o deselezionare una casella di controllo all'interno del documento.

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

## Passaggio 3: aggiungere un controllo del contenuto del tipo di casella di controllo
 Creare un`StructuredDocumentTag` con`SdtType.Checkbox` per rappresentare il controllo del contenuto della casella di controllo. Specificare`MarkupLevel.Inline` inserirlo all'interno del testo.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Passaggio 4: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Codice sorgente di esempio per il controllo del contenuto del tipo di casella di controllo utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Questo è tutto! Hai creato correttamente un controllo del contenuto del tipo di casella di controllo nel documento di Word utilizzando Aspose.Words per .NET.