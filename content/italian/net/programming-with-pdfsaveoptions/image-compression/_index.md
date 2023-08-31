---
title: Compressione delle immagini in un documento PDF
linktitle: Compressione delle immagini in un documento PDF
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida passo passo alla compressione delle immagini in un documento PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/image-compression/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzione Compressione immagine in un documento PDF con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come comprimere le immagini in un documento e generare un PDF con una corretta compressione delle immagini.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio, supponiamo che il documento si chiami "Rendering.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: configurare le opzioni di salvataggio come PDF con la compressione delle immagini

 Per comprimere le immagini durante la conversione in PDF, dobbiamo configurare il file`PdfSaveOptions` oggetto. Possiamo impostare il tipo di compressione dell'immagine, la qualità JPEG e altre opzioni di conformità PDF, se necessario.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Passaggio 4: salva il documento come PDF con la compressione delle immagini

Infine, possiamo salvare il documento in formato PDF utilizzando le opzioni di salvataggio configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Passaggio 5: configurare le opzioni per il salvataggio in PDF/A-2u con compressione delle immagini

Se desideri generare PDF conforme a PDF/A-2u con compressione delle immagini, puoi configurare le opzioni di salvataggio aggiuntive.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Usa la compressione JPEG con una qualità del 50% per ridurre le dimensioni del file.
};
```

## Passaggio 6: salvare il documento come PDF/A-2u con compressione dell'immagine

Salvare il documento in formato PDF/A-2u utilizzando le opzioni di salvataggio aggiuntive configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



È tutto ! Hai compresso correttamente le immagini in un documento e generato un PDF con una corretta compressione delle immagini utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per la compressione di immagini con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Usa la compressione JPEG con una qualità del 50% per ridurre le dimensioni del file.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Conclusione

In questo tutorial, abbiamo spiegato come comprimere le immagini in un documento PDF utilizzando Aspose.Words per .NET. Seguendo i passaggi descritti, puoi facilmente ridurre le dimensioni delle immagini nel tuo documento PDF e generare un PDF con una corretta compressione delle immagini. Usa le funzionalità di compressione delle immagini di Aspose.Words per .NET per ottimizzare le dimensioni dei tuoi documenti PDF preservando la qualità dell'immagine.

### Domande frequenti

#### D: Cos'è la compressione delle immagini in un documento PDF?
R: La compressione delle immagini in un documento PDF consiste nel ridurre le dimensioni delle immagini incluse nel documento PDF per ridurre le dimensioni complessive del file PDF. Ciò riduce lo spazio di archiviazione necessario e migliora le prestazioni durante il caricamento e la visualizzazione del PDF.

#### D: Come posso comprimere le immagini in un documento PDF con Aspose.Words per .NET?
R: Per comprimere le immagini in un documento PDF con Aspose.Words per .NET, attenersi alla seguente procedura:

 Crea un'istanza di`Document` class che specifica il percorso del documento Word.

 Crea un'istanza di`PdfSaveOptions`classe e impostare il`ImageCompression` proprietà a`PdfImageCompression.Jpeg` per utilizzare la compressione JPEG.

È inoltre possibile impostare altre opzioni di compressione dell'immagine, come la qualità JPEG, in base alle proprie esigenze.

 Usa il`Save` metodo del`Document`class per salvare il documento in formato PDF specificando le opzioni di salvataggio.

#### D: Qual è la differenza tra la compressione delle immagini standard e la compressione delle immagini PDF/A-2u?
R: La compressione delle immagini standard riduce le dimensioni delle immagini in un documento PDF preservando i campi del modulo. Ciò riduce le dimensioni complessive del file PDF senza compromettere la funzionalità del campo modulo.

Compressione immagine con PDF/A-2u è un'opzione aggiuntiva che consente di generare un file PDF conforme allo standard PDF/A-2u durante l'applicazione della compressione dell'immagine. PDF/A-2u è uno standard ISO per l'archiviazione di documenti PDF e garantisce la conservazione a lungo termine dei documenti.
