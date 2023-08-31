---
title: Incorpora caratteri sottoinsieme nel documento PDF
linktitle: Incorpora caratteri sottoinsieme nel documento PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per incorporare sottoinsiemi di caratteri in un documento PDF utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzionalità di incorporamento del sottoinsieme di caratteri con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial sarai in grado di capire come incorporare sottoinsiemi di caratteri in un documento e generare un PDF contenente solo i glifi utilizzati nel documento.

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

## Passaggio 3: configura le opzioni di salvataggio come PDF

 Per creare un PDF contenente solo i sottoinsiemi di font utilizzati nel documento, dobbiamo configurare il file`PdfSaveOptions` oggetto con il`EmbedFullFonts` proprietà impostata su`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Passaggio 4: salva il documento come PDF con sottoinsiemi di caratteri

 Infine, possiamo salvare il documento come PDF utilizzando i sottoinsiemi di caratteri. Specificare il nome del file di output e il file`saveOptions` oggetto che abbiamo configurato nel passaggio precedente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

È tutto ! Hai incorporato con successo sottoinsiemi di caratteri in un documento e generato un PDF contenente solo i glifi utilizzati nel documento con Aspose.Words per .NET.

### Codice sorgente di esempio per incorporare sottoinsiemi di caratteri con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Il PDF di output conterrà sottoinsiemi di caratteri nel documento.
	// Solo i glifi utilizzati nel documento sono inclusi nei caratteri PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Conclusione

In questo tutorial, abbiamo imparato come incorporare sottoinsiemi di caratteri in un documento PDF utilizzando Aspose.Words per .NET. Incorporare sottoinsiemi di caratteri aiuta a ridurre le dimensioni del file PDF preservando l'aspetto del documento utilizzando solo i caratteri effettivamente utilizzati. Ciò garantisce migliore compatibilità e prestazioni durante la visualizzazione e la stampa del PDF. Sentiti libero di esplorare ulteriormente le funzionalità di Aspose.Words per .NET per ottimizzare la generazione dei tuoi documenti PDF con sottoinsiemi di caratteri incorporati.

### Domande frequenti

#### D: Che cosa significa incorporare sottoinsiemi di caratteri in un documento PDF?
R: L'incorporamento di sottoinsiemi di caratteri in un documento PDF è il processo che include solo i glifi utilizzati nel documento, anziché includere tutti i caratteri completi. Ciò riduce la dimensione del file PDF includendo solo i dati dei font necessari per visualizzare i caratteri effettivamente utilizzati nel documento.

#### D: Qual è la differenza tra l'incorporamento di caratteri completi e l'incorporamento di sottoinsiemi di caratteri?
R: L'incorporamento completo dei caratteri significa includere tutti i caratteri utilizzati nel documento nel file PDF, il che garantisce che il documento verrà visualizzato esattamente come è stato progettato, ma può aumentare le dimensioni del file PDF. Al contrario, l'incorporamento di sottoinsiemi di caratteri contiene solo i glifi utilizzati nel documento, riducendo così la dimensione del file PDF, ma limitando la capacità di replicare esattamente l'aspetto del documento se vengono aggiunti ulteriori caratteri in seguito.

#### D: Come posso incorporare sottoinsiemi di caratteri in un documento PDF utilizzando Aspose.Words per .NET?
R: Per incorporare sottoinsiemi di caratteri in un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Imposta il percorso della directory del documento sostituendolo`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Carica il documento che desideri elaborare utilizzando il file`Document` classe e il percorso del documento.

 Configura le opzioni di salvataggio del PDF creando un'istanza del file`PdfSaveOptions` classe e impostando il file`EmbedFullFonts` proprietà a`false`Ciò garantisce che solo i sottoinsiemi di caratteri utilizzati nel documento verranno inclusi nel file PDF.

 Salva il documento in formato PDF con i sottoinsiemi di caratteri incorporati utilizzando il file`Save` metodo del`Document` oggetto, specificando il nome del file di output e le opzioni di salvataggio configurate in precedenza.

#### D: Quali sono i vantaggi derivanti dall'incorporamento di sottoinsiemi di caratteri in un documento PDF?
R: I vantaggi derivanti dall'incorporamento di sottoinsiemi di caratteri in un documento PDF sono:

Dimensioni file PDF ridotte: includendo solo i glifi utilizzati nel documento, le dimensioni del file PDF vengono ridotte rispetto all'incorporamento di caratteri completi.

Conservazione dell'aspetto del documento: i sottoinsiemi di caratteri inclusi nel file PDF consentono di riprodurre l'aspetto del documento utilizzando solo i caratteri effettivamente utilizzati.

Compatibilità con le restrizioni della licenza: l'incorporamento di sottoinsiemi di caratteri può essere preferibile nei casi in cui i caratteri completi non possono essere incorporati legalmente a causa di restrizioni di licenza.