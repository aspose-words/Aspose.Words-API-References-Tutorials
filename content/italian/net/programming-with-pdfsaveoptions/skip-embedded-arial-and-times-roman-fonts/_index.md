---
title: Ottimizza le dimensioni del PDF con Salta i caratteri Arial e Times Roman incorporati
linktitle: Ottimizza le dimensioni del PDF con Salta i caratteri Arial e Times Roman incorporati
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per generare PDF ottimizzati senza incorporare i caratteri Arial e Times Roman con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Questo articolo fornisce una guida dettagliata su come utilizzare la funzione per ottimizzare le dimensioni del PDF saltando i caratteri Arial e Times Roman incorporati alla dimensione del metafile con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come configurare l'opzione della modalità di incorporamento dei caratteri in un documento e generare un PDF senza incorporare i caratteri Arial e Times Roman.

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

## Passaggio 3: configurare le opzioni di salvataggio come PDF con l'incorporamento dei caratteri

 Per saltare l'incorporamento dei caratteri Arial e Times Roman nel PDF generato, dobbiamo configurare il file`PdfSaveOptions` oggetto e impostare il`FontEmbeddingMode` proprietà a`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Passaggio 4: salva il documento come PDF senza caratteri incorporati

Infine, possiamo salvare il documento in formato PDF utilizzando le opzioni di salvataggio configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

È tutto ! Hai generato correttamente un PDF senza incorporare i caratteri Arial e Times Roman utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per ignorare i caratteri Arial e Times Roman incorporati nelle dimensioni del metafile con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Conclusione

In questo tutorial, abbiamo spiegato come disabilitare l'incorporamento dei font Arial e Times Roman in un documento PDF utilizzando Aspose.Words per .NET. Seguendo i passaggi descritti, puoi generare un file PDF senza incorporare questi caratteri specifici, il che può aiutare a ridurre le dimensioni del file e garantire una migliore compatibilità dei documenti su piattaforme diverse. Assicurati di considerare le conseguenze della disabilitazione dell'incorporamento dei caratteri quando utilizzi questa funzione. Sentiti libero di esplorare più funzionalità di Aspose.Words per .NET per ottimizzare la generazione dei tuoi file PDF.

### Domande frequenti

#### D: Cosa disabilita l'incorporamento dei caratteri Arial e Times Roman in un documento PDF e perché è importante?
R: Disabilitare l'incorporamento dei font Arial e Times Roman in un documento PDF è il processo per non includere questi font nel file PDF generato. Questo può essere importante per ridurre le dimensioni del file PDF evitando di includere caratteri che sono già comunemente disponibili sui sistemi di lettura PDF. Può anche aiutare a garantire una migliore compatibilità e un aspetto coerente del documento PDF su diversi dispositivi e piattaforme.

#### D: Come posso configurare Aspose.Words per .NET in modo che non incorpori i caratteri Arial e Times Roman in un documento PDF?
R: Per configurare Aspose.Words per .NET in modo che non incorpori i font Arial e Times Roman in un documento PDF, segui questi passaggi:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Caricare il documento che si desidera elaborare utilizzando il file`Document` class e il percorso del documento specificato.

 Crea un'istanza di`PdfSaveOptions`classe e impostare il`FontEmbeddingMode` proprietà a`PdfFontEmbeddingMode.EmbedAll`. Questo incorporerà tutti i caratteri tranne Arial e Times Roman nel file PDF generato.

 Usa il`Save` metodo del`Document` oggetto di salvare il documento in formato PDF specificando le opzioni di salvataggio configurate in precedenza.

#### D: Quali sono i vantaggi della disabilitazione dell'incorporamento dei caratteri Arial e Times Roman in un documento PDF?
R: I vantaggi della disabilitazione dell'incorporamento dei caratteri Arial e Times Roman in un documento PDF sono:

Riduzione delle dimensioni dei file PDF: evitando di incorporare caratteri comunemente disponibili come Arial e Times Roman, è possibile ridurre le dimensioni dei file PDF, semplificando l'archiviazione, la condivisione e il trasferimento dei file.

Migliore compatibilità: utilizzando i caratteri comunemente disponibili sui sistemi di lettura PDF, garantisci una migliore compatibilità e aspetto del documento su diversi dispositivi e piattaforme.

#### D: Quali sono le conseguenze della disabilitazione dell'incorporamento dei font Arial e Times Roman in un documento PDF?
R: Le conseguenze della disabilitazione dell'incorporamento dei font Arial e Times Roman in un documento PDF sono le seguenti:

Aspetto diverso: se i caratteri Arial e Times Roman non sono disponibili sul sistema in cui viene aperto il PDF, verranno utilizzati caratteri sostitutivi, che potrebbero risultare in un aspetto diverso da quello previsto.

Problemi di leggibilità: i caratteri sostitutivi utilizzati potrebbero non essere leggibili come i caratteri in origine, il che potrebbe influire sulla leggibilità del documento.