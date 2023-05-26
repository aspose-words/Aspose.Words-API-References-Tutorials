---
title: Stato corrente della casella di controllo
linktitle: Stato corrente della casella di controllo
second_title: Riferimento all'API Aspose.Words per .NET
description: Informazioni su come recuperare e impostare lo stato corrente di un controllo del contenuto di una casella di controllo in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/current-state-of-check-box/
---

Questo tutorial spiega come recuperare e impostare lo stato corrente di un controllo del contenuto di una casella di controllo in un documento di Word utilizzando Aspose.Words per .NET. Puoi selezionare o deselezionare la casella di controllo in base al suo stato attuale.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e recuperare il controllo del contenuto della casella di controllo
 Carica il documento Word usando il file`Document` costruttore, passando il percorso al documento come parametro. Quindi, recuperare il controllo del contenuto della casella di controllo desiderato dal documento. In questo esempio, assumiamo che la casella di controllo sia il primo tag di documento strutturato nel documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Passaggio 3: selezionare o deselezionare la casella di controllo in base al suo stato attuale
 Controlla se il tag del documento strutturato recuperato è di tipo`SdtType.Checkbox` . Se lo è, impostare il`Checked` proprietà del controllo contenuto a`true` per selezionare la casella. Altrimenti, puoi lasciarlo deselezionato.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Passaggio 4: salvare il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save`metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Codice sorgente di esempio per Current State Of Check Box utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Ottenere il primo controllo del contenuto dal documento.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Questo è tutto! Hai recuperato e impostato correttamente lo stato corrente di un controllo del contenuto della casella di controllo nel documento di Word utilizzando Aspose.Words per .NET.