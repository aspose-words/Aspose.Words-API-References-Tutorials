---
title: Ottimizza le dimensioni del PDF con Salta i caratteri Arial e Times Roman incorporati
linktitle: Ottimizza le dimensioni del PDF con Salta i caratteri Arial e Times Roman incorporati
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per generare PDF ottimizzati senza incorporare i caratteri Arial e Times Roman con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzionalità per ottimizzare le dimensioni del PDF saltando i caratteri Arial e Times Roman incorporati nella dimensione del metafile con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Al termine di questo tutorial sarai in grado di capire come configurare l'opzione della modalità di incorporamento dei caratteri in un documento e generare un PDF senza incorporare i caratteri Arial e Times Roman.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. È possibile trovare la libreria e le istruzioni di installazione sul sito Web Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio presupponiamo che il documento si chiami "Rendering.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: configura le opzioni di salvataggio come PDF con l'incorporamento dei caratteri

 Per evitare di incorporare i caratteri Arial e Times Roman nel PDF generato, dobbiamo configurare il file`PdfSaveOptions` oggetto e impostare il`FontEmbeddingMode` proprietà a`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Passaggio 4: salva il documento come PDF senza caratteri incorporati

Infine, possiamo salvare il documento in formato PDF utilizzando le opzioni di salvataggio configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

È tutto ! Hai generato con successo un PDF senza incorporare i caratteri Arial e Times Roman utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per ignorare i caratteri Arial e Times Roman incorporati alla dimensione del metafile con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Conclusione

In questo tutorial, abbiamo spiegato come disabilitare l'incorporamento dei caratteri Arial e Times Roman in un documento PDF utilizzando Aspose.Words per .NET. Seguendo i passaggi descritti, puoi generare un file PDF senza incorporare questi caratteri specifici, il che può aiutare a ridurre le dimensioni del file e garantire una migliore compatibilità dei documenti su diverse piattaforme. Assicurati di considerare le conseguenze della disabilitazione dell'incorporamento dei caratteri quando usi questa funzione. Sentiti libero di esplorare altre funzionalità di Aspose.Words per .NET per ottimizzare la generazione dei tuoi file PDF.

### Domande frequenti

#### D: Che cosa significa disabilitare l'incorporamento dei caratteri Arial e Times Roman in un documento PDF e perché è importante?
R: Disabilitare l'incorporamento dei caratteri Arial e Times Roman in un documento PDF significa non includere questi caratteri nel file PDF generato. Questo può essere importante per ridurre la dimensione del file PDF evitando di includere caratteri già comunemente disponibili sui sistemi di lettura PDF. Può anche contribuire a garantire una migliore compatibilità e un aspetto coerente del documento PDF su diversi dispositivi e piattaforme.

#### D: Come posso configurare Aspose.Words per .NET per non incorporare i caratteri Arial e Times Roman in un documento PDF?
R: Per configurare Aspose.Words per .NET per non incorporare i caratteri Arial e Times Roman in un documento PDF, attenersi alla seguente procedura:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Carica il documento che desideri elaborare utilizzando il file`Document` classe e il percorso del documento specificato.

 Crea un'istanza di`PdfSaveOptions`classe e impostare il file`FontEmbeddingMode` proprietà a`PdfFontEmbeddingMode.EmbedAll`. Ciò incorporerà tutti i caratteri tranne Arial e Times Roman nel file PDF generato.

 Usa il`Save` metodo del`Document` oggetto di salvare il documento in formato PDF specificando le opzioni di salvataggio configurate in precedenza.

#### D: Quali sono i vantaggi derivanti dalla disabilitazione dell'incorporamento dei caratteri Arial e Times Roman in un documento PDF?
R: I vantaggi derivanti dalla disabilitazione dell'incorporamento dei caratteri Arial e Times Roman in un documento PDF sono:

Riduzione delle dimensioni dei file PDF: evitando di incorporare caratteri comunemente disponibili come Arial e Times Roman, è possibile ridurre le dimensioni dei file PDF, semplificando l'archiviazione, la condivisione e il trasferimento dei file.

Migliore compatibilità: utilizzando i caratteri comunemente disponibili sui sistemi di lettura PDF, garantisci una migliore compatibilità e aspetto del documento su diversi dispositivi e piattaforme.

#### D: Quali sono le conseguenze della disattivazione dell'incorporamento dei caratteri Arial e Times Roman in un documento PDF?
R: Le conseguenze della disabilitazione dell'incorporamento dei caratteri Arial e Times Roman in un documento PDF sono le seguenti:

Aspetto diverso: se i caratteri Arial e Times Roman non sono disponibili nel sistema in cui viene aperto il PDF, verranno utilizzati caratteri sostitutivi, il che potrebbe comportare un aspetto diverso da quello previsto.

Problemi di leggibilità: i caratteri sostitutivi utilizzati potrebbero non essere leggibili come i caratteri originali, il che potrebbe influire sulla leggibilità del documento.