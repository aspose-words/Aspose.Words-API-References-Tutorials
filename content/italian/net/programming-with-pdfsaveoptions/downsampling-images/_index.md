---
title: Riduci le dimensioni del documento PDF con il downsampling delle immagini
linktitle: Riduci le dimensioni del documento PDF con il downsampling delle immagini
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come ridurre le dimensioni del documento PDF con il downsampling delle immagini durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/downsampling-images/
---

In questo tutorial, ti guideremo attraverso i passaggi per ridurre le dimensioni del documento PDF con il downsampling delle immagini durante la conversione in PDF con Aspose.Words per .NET. Ciò riduce la dimensione del file PDF generato. Seguire i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del documento.

## Passaggio 2: configura le opzioni di salvataggio del PDF

Crea un'istanza della classe PdfSaveOptions e imposta le opzioni di ridimensionamento dell'immagine:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 IL`Resolution` specifica la risoluzione target delle immagini e il file`ResolutionThreshold`La proprietà specifica la risoluzione minima al di sotto della quale le immagini non verranno ridimensionate.

## Passaggio 3: converti il documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di salvataggio:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Codice sorgente di esempio per il downsampling delle immagini utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Possiamo impostare una soglia minima per il downsampling.
	// Questo valore impedirà il downsampling della seconda immagine nel documento di input.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Seguendo questi passaggi, puoi facilmente ridurre la risoluzione dell'immagine durante la conversione in PDF con Aspose.Words per .NET.

## Conclusione

In questo tutorial, abbiamo spiegato come ridurre le dimensioni di un documento PDF con il campionamento delle immagini durante la conversione in PDF utilizzando Aspose.Words per .NET. Seguendo i passaggi descritti, puoi facilmente ridurre la risoluzione delle immagini e la dimensione del file PDF generato. Assicurati di specificare il percorso corretto del documento e di configurare le opzioni di campionamento dell'immagine secondo necessità. La riduzione delle dimensioni del file PDF semplifica la condivisione, l'archiviazione e il caricamento rapido del file su piattaforme diverse. Goditi i vantaggi di ridurre le dimensioni del documento PDF con il campionamento delle immagini utilizzando Aspose.Words per .NET.

### Domande frequenti

#### D: Che cosa significa ridurre le dimensioni del documento PDF con il campionamento delle immagini?
R: Ridurre le dimensioni del documento PDF con il campionamento delle immagini significa diminuire le dimensioni del file PDF generato riducendo la risoluzione delle immagini durante la conversione in PDF. Ciò ottimizza l'uso dello spazio di archiviazione e semplifica la condivisione e il trasferimento del file PDF.

#### D: Come posso ridurre le dimensioni del documento PDF con il campionamento delle immagini utilizzando Aspose.Words per .NET?
R: Per ridurre le dimensioni del documento PDF con il campionamento delle immagini utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Carica il documento che desideri convertire in PDF utilizzando il file`Document` class e specificare il percorso del documento nella directory dei documenti specificata.

 Configura le opzioni di salvataggio come PDF creando un'istanza del file`PdfSaveOptions` classe e impostando le opzioni di campionamento dell'immagine utilizzando il file`DownsampleOptions` proprietà. È possibile specificare la risoluzione target delle immagini utilizzando il file`Resolution` proprietà e impostare una soglia di risoluzione minima al di sopra della quale le immagini non verranno ridimensionate utilizzando la proprietà`ResolutionThreshold` proprietà.

 Salvare il documento in formato PDF utilizzando il file`Save` metodo del`Document`classe specificando il percorso e le opzioni di salvataggio.

#### D: Quali sono i vantaggi derivanti dalla riduzione delle dimensioni del documento PDF con il campionamento delle immagini?
R: I vantaggi derivanti dalla riduzione delle dimensioni del documento PDF con il campionamento delle immagini sono:

Dimensioni file PDF ridotte: il campionamento delle immagini riduce la risoluzione delle immagini nel documento PDF, determinando una significativa diminuzione delle dimensioni del file PDF. Ciò semplifica la condivisione e il trasferimento del file, soprattutto via e-mail o online.

Ottimizzazione dello spazio di archiviazione: ridurre le dimensioni del file PDF aiuta a ottimizzare l'uso dello spazio di archiviazione, soprattutto quando si hanno molti file PDF contenenti immagini ad alta risoluzione.

Miglioramenti delle prestazioni: i file PDF più piccoli vengono caricati più velocemente e possono essere aperti e visualizzati più velocemente su dispositivi diversi.