---
title: Conversione in PDF 17
linktitle: Conversione in PDF 17
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire documenti in PDF 1.7 con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

In questo tutorial, ti guideremo attraverso i passaggi per convertire in PDF 1.7 con Aspose.Words per .NET. La conversione in PDF 1.7 consente di generare file PDF conformi allo standard PDF 1.7. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del documento.

## Passaggio 2: imposta le opzioni di conversione PDF

Crea un'istanza della classe PdfSaveOptions e specifica la versione dello standard PDF che desideri utilizzare:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Questa opzione assicura che il file PDF generato sia conforme allo standard PDF 1.7.

## Passo 3: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di conversione:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Esempio di codice sorgente per Conversion To Pdf 17 utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per convertire in PDF 1.7 con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Seguendo questi passaggi, puoi convertire facilmente in PDF 1.7 con Aspose.Words per .NET.

