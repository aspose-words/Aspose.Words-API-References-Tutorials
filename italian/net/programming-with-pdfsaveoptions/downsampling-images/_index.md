---
title: Sottocampionamento delle immagini
linktitle: Sottocampionamento delle immagini
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come ridurre la risoluzione dell'immagine durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/downsampling-images/
---

In questo tutorial, ti guideremo attraverso i passaggi per ridurre la risoluzione dell'immagine durante la conversione in PDF con Aspose.Words per .NET. Ciò riduce le dimensioni del file PDF generato. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del documento.

## Passaggio 2: configurare le opzioni di salvataggio PDF

Crea un'istanza della classe PdfSaveOptions e imposta le opzioni di ridimensionamento dell'immagine:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 IL`Resolution` La proprietà specifica la risoluzione di destinazione delle immagini e il`ResolutionThreshold` La proprietà specifica la risoluzione minima al di sotto della quale le immagini non verranno ridimensionate.

## Passo 3: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di salvataggio:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Esempio di codice sorgente per il downsampling delle immagini utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//Possiamo impostare una soglia minima per il downsampling.
	// Questo valore impedirà il downsampling della seconda immagine nel documento di input.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Seguendo questi passaggi, puoi facilmente ridurre la risoluzione dell'immagine durante la conversione in PDF con Aspose.Words per .NET.


