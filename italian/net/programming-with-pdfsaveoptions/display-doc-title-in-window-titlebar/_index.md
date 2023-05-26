---
title: Visualizza il titolo del documento nella barra del titolo della finestra
linktitle: Visualizza il titolo del documento nella barra del titolo della finestra
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come visualizzare il titolo del documento nella barra del titolo della finestra durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

In questo tutorial, ti guideremo attraverso i passaggi per visualizzare il titolo del documento nella barra del titolo della finestra con Aspose.Words per .NET. Questa funzione consente di visualizzare il titolo del documento nella barra del titolo della finestra quando si apre il documento PDF generato. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del documento.

## Passaggio 2: configurare le opzioni di salvataggio PDF

Creare un'istanza della classe PdfSaveOptions e abilitare la visualizzazione del titolo del documento nella barra del titolo della finestra:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Questa opzione abilita la visualizzazione del titolo del documento nella barra del titolo della finestra durante la conversione in PDF.

## Passo 3: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di conversione:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Esempio di codice sorgente per Display Doc Title In Window Titlebar utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per visualizzare il titolo del documento nella barra del titolo della finestra in un documento PDF con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Seguendo questi passaggi, puoi visualizzare facilmente il titolo del documento nella barra del titolo della finestra durante la conversione in PDF con Aspose.Words per .NET.

