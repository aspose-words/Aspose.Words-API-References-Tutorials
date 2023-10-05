---
title: Riduci le dimensioni del PDF con i caratteri Wmf ridimensionati alle dimensioni del metafile
linktitle: Riduci le dimensioni del PDF con i caratteri Wmf ridimensionati alle dimensioni del metafile
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per ridurre le dimensioni del PDF con i caratteri wmf ridimensionati alle dimensioni del metafile durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Questo articolo fornisce una guida passo passo su come ridurre le dimensioni del pdf con la funzione di ridimensionamento dei caratteri wmf alla dimensione del metafile con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come abilitare o disabilitare il ridimensionamento dei caratteri WMF durante la conversione in PDF.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. È possibile trovare la libreria e le istruzioni di installazione sul sito Web Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio presupponiamo che il documento si chiami "WMF con text.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Passaggio 3: configura le opzioni di rendering del metafile

 Per abilitare o disabilitare il ridimensionamento dei caratteri WMF alla dimensione del metafile, dobbiamo configurare il file`MetafileRenderingOptions`oggetto. In questo esempio, disabilitiamo il ridimensionamento dei caratteri impostando il file`ScaleWmfFontsToMetafileSize`proprietà a`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Passaggio 4: configura le opzioni di salvataggio come PDF con le opzioni di rendering del metafile

Infine, possiamo configurare le opzioni di salvataggio in PDF utilizzando le opzioni di rendering del metafile configurate in precedenza.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Passaggio 5: salva il documento come PDF con le opzioni di rendering metafile

Salvare il documento in formato PDF utilizzando le opzioni di salvataggio precedentemente configurate.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

È tutto ! Hai abilitato o disabilitato con successo il ridimensionamento dei caratteri WMF alla dimensione del metafile durante la conversione

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

	// Se Aspose.Words non riesce a eseguire correttamente il rendering di alcuni record del metafile in grafica vettoriale
	// quindi Aspose.Words esegue il rendering di questo metafile in una bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Conclusione

In questo tutorial, abbiamo spiegato come abilitare o disabilitare il ridimensionamento dei caratteri WMF alla dimensione del metafile in un documento PDF utilizzando Aspose.Words per .NET. Seguendo i passaggi descritti, puoi facilmente controllare se i caratteri WMF devono essere ridimensionati per corrispondere alla dimensione del metafile durante la conversione in un documento PDF. Ciò può aiutarti a ridurre le dimensioni del file PDF generato e a migliorare le prestazioni di rendering. Assicurati di specificare il percorso corretto dei tuoi documenti e di configurare le opzioni di rendering del metafile secondo necessità.

### Domande frequenti

#### D: Che cosa significa ridimensionare i caratteri WMF alle dimensioni del metafile in un documento PDF?
R: Il ridimensionamento dei caratteri WMF alla dimensione del metafile in un documento PDF è una funzionalità che controlla se i caratteri WMF devono essere ridimensionati per corrispondere alla dimensione del metafile durante la conversione in un documento PDF. Quando questa funzionalità è abilitata, i caratteri WMF vengono ridimensionati per corrispondere alla dimensione del metafile, il che potrebbe ridurre la dimensione del documento PDF generato.

#### D: Come posso utilizzare Aspose.Words per .NET per abilitare o disabilitare il ridimensionamento dei caratteri WMF alla dimensione del metafile in un documento PDF?
R: Per abilitare o disabilitare il ridimensionamento dei caratteri WMF alla dimensione del metafile in un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Carica il documento che desideri elaborare utilizzando il file`Document` class e specificare il percorso del documento Word nella directory dei documenti specificata.

 Configura le opzioni di rendering del metafile creando un'istanza del file`MetafileRenderingOptions` classe e impostando il file`ScaleWmfFontsToMetafileSize`proprietà a`true` per abilitare il ridimensionamento dei caratteri WMF alla dimensione del metafile o a`false` per disattivare questa funzione.

 Configura le opzioni di salvataggio come PDF creando un'istanza del file`PdfSaveOptions` class e utilizzando le opzioni di rendering del metafile configurate in precedenza.

 Salvare il documento in formato PDF utilizzando il file`Save` metodo del`Document` classe specificando il percorso e le opzioni di salvataggio.

#### D: Quali sono i vantaggi del ridimensionamento dei caratteri WMF alle dimensioni del metafile in un documento PDF?
R: I vantaggi derivanti dal ridimensionamento dei caratteri WMF alle dimensioni del metafile in un documento PDF sono:

Riduzione della dimensione del file PDF: il ridimensionamento dei caratteri WMF alla dimensione del metafile può ridurre la dimensione del documento PDF generato adattando la dimensione del carattere alle esigenze del metafile.

Prestazioni migliorate: adattando la dimensione dei caratteri WMF alle dimensioni del metafile, il rendering del documento PDF può essere più rapido ed efficiente.