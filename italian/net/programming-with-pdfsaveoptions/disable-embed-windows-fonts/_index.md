---
title: Disabilita Incorpora caratteri di Windows
linktitle: Disabilita Incorpora caratteri di Windows
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come disabilitare l'incorporamento dei caratteri di Windows durante la conversione di documenti in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

In questo tutorial, ti guideremo attraverso i passaggi per disabilitare l'incorporamento dei caratteri di Windows in un documento PDF con Aspose.Words per .NET. Disabilitando l'incorporamento dei caratteri, puoi ridurre le dimensioni del file PDF generato. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del documento.

## Passaggio 2: imposta le opzioni di salvataggio del PDF

Crea un'istanza della classe PdfSaveOptions e specifica come incorporare i font:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Questa opzione consente di disattivare l'integrazione dei font Windows nel file PDF generato.

## Passo 3: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di conversione:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Codice sorgente di esempio per disabilitare i caratteri incorporati di Windows utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per disabilitare l'incorporamento dei font Windows in un documento PDF con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Il PDF di output verrà salvato senza incorporare i caratteri Windows standard.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Seguendo questi passaggi, puoi facilmente disabilitare l'incorporamento dei caratteri Windows in un documento PDF con Aspose.Words per .NET.

