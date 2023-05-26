---
title: Posizionamento del testo aggiuntivo
linktitle: Posizionamento del testo aggiuntivo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come controllare il posizionamento di testo aggiuntivo durante la conversione di documenti Word in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità aggiuntiva di posizionamento del testo con Aspose.Words per .NET. Questa funzione consente di controllare il posizionamento del testo aggiuntivo durante la conversione di un documento Word in PDF. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento Word che vuoi convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del tuo documento Word.

## Passaggio 2: imposta le opzioni di conversione PDF

Crea un'istanza della classe PdfSaveOptions e abilita il posizionamento del testo aggiuntivo:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

Questa opzione controlla il posizionamento preciso del testo aggiuntivo nel PDF.

## Passo 3: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento Word in PDF specificando le opzioni di conversione:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Codice sorgente di esempio per il posizionamento del testo aggiuntivo utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per utilizzare la funzionalità aggiuntiva di posizionamento del testo con Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
Seguendo questi passaggi, puoi facilmente controllare il posizionamento del testo aggiuntivo durante la conversione di un documento Word in PDF con Aspose.Words per .NET.

