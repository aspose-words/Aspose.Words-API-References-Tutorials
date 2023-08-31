---
title: Casella di controllo Stato corrente
linktitle: Casella di controllo Stato corrente
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come recuperare e impostare lo stato corrente di un controllo del contenuto di una casella di controllo in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/current-state-of-check-box/
---

Questo tutorial spiega come recuperare e impostare lo stato corrente di un controllo del contenuto della casella di controllo in un documento di Word utilizzando Aspose.Words per .NET. Puoi selezionare o deselezionare la casella di controllo in base al suo stato corrente.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e recuperare il controllo del contenuto della casella di controllo
 Caricare il documento Word utilizzando il file`Document` costruttore, passando il percorso del documento come parametro. Quindi, recuperare il controllo del contenuto della casella di controllo desiderata dal documento. In questo esempio presupponiamo che la casella di controllo sia il primo tag di documento strutturato nel documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Passaggio 3: seleziona o deseleziona la casella di controllo in base al suo stato corrente
 Controlla se il tag del documento strutturato recuperato è di tipo`SdtType.Checkbox` . Se lo è, imposta il file`Checked` proprietà del controllo contenuto a`true` per selezionare la casella. Altrimenti puoi lasciarlo deselezionato.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Passaggio 4: salva il documento
 Salvare il documento modificato nella directory specificata utilizzando il file`Save`metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Codice sorgente di esempio per la casella di controllo Stato corrente utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Ottieni il primo controllo del contenuto dal documento.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Questo è tutto! Hai recuperato e impostato con successo lo stato corrente di un controllo del contenuto della casella di controllo nel tuo documento Word utilizzando Aspose.Words per .NET.