---
title: Ridimensiona i caratteri Wmf alla dimensione del metafile
linktitle: Ridimensiona i caratteri Wmf alla dimensione del metafile
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo-passo per regolare la dimensione del carattere WMF durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Questo articolo fornisce una guida dettagliata su come utilizzare la funzionalità WMF Font Scaling to Metafile Size con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come abilitare o disabilitare il ridimensionamento dei caratteri WMF durante la conversione in PDF.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio, supponiamo che il documento si chiami "WMF con text.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Passaggio 3: configurare le opzioni di rendering del metafile

 Per abilitare o disabilitare il ridimensionamento dei caratteri WMF alla dimensione del metafile, è necessario configurare il file`MetafileRenderingOptions` oggetto. In questo esempio, disabilitiamo il ridimensionamento dei caratteri impostando il`ScaleWmfFontsToMetafileSize` proprietà a`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Passaggio 4: configurare le opzioni di salvataggio come PDF con le opzioni di rendering del metafile

Infine, possiamo configurare le opzioni di salvataggio in PDF utilizzando le opzioni di rendering del metafile configurate in precedenza.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Passaggio 5: salva il documento come PDF con le opzioni di rendering del metafile

Salva il documento in formato PDF utilizzando le opzioni di salvataggio precedentemente configurate.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

È tutto ! Hai abilitato o disabilitato correttamente il ridimensionamento dei caratteri WMF alla dimensione del metafile durante la conversione

un documento PDF utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per ridimensionare i caratteri WMF alla dimensione del metafile con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Se Aspose.Words non è in grado di eseguire correttamente il rendering di alcuni dei record del metafile in grafica vettoriale
	// quindi Aspose.Words esegue il rendering di questo metafile in una bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```
