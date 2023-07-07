---
title: Incorpora sottoinsiemi di caratteri nel documento PDF
linktitle: Incorpora sottoinsiemi di caratteri nel documento PDF
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per incorporare sottoinsiemi di caratteri in un documento PDF utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Questo articolo fornisce una guida dettagliata su come utilizzare la funzione di incorporamento di sottoinsiemi di caratteri con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come incorporare sottoinsiemi di caratteri in un documento e generare un PDF contenente solo i glifi utilizzati nel documento.

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

## Passaggio 3: configurare le opzioni di salvataggio come PDF

 Per creare un PDF contenente solo i sottoinsiemi di caratteri utilizzati nel documento, è necessario configurare il file`PdfSaveOptions` oggetto con il`EmbedFullFonts` proprietà impostata su`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Passaggio 4: salva il documento come PDF con sottoinsiemi di caratteri

 Infine, possiamo salvare il documento come PDF utilizzando i sottoinsiemi di caratteri. Specificare il nome del file di output e il file`saveOptions` oggetto che abbiamo configurato nel passaggio precedente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

È tutto ! Hai incorporato correttamente sottoinsiemi di caratteri in un documento e generato un PDF contenente solo i glifi utilizzati nel documento con Aspose.Words per .NET.

### Esempio di codice sorgente per l'incorporamento di sottoinsiemi di caratteri con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Il PDF di output conterrà sottoinsiemi dei caratteri nel documento.
	// Nei font PDF sono inclusi solo i glifi utilizzati nel documento.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Conclusione

In questo tutorial, abbiamo imparato come incorporare sottoinsiemi di caratteri in un documento PDF utilizzando Aspose.Words per .NET. L'incorporamento di sottoinsiemi di font consente di ridurre le dimensioni del file PDF preservando l'aspetto del documento utilizzando solo i caratteri effettivamente utilizzati. Ciò garantisce una migliore compatibilità e prestazioni durante la visualizzazione e la stampa del PDF. Sentiti libero di esplorare ulteriormente le funzionalità di Aspose.Words per .NET per ottimizzare la generazione dei tuoi documenti PDF con sottoinsiemi di font incorporati.

### Domande frequenti

#### D: Cos'è l'incorporamento di sottoinsiemi di font in un documento PDF?
R: L'incorporamento di sottoinsiemi di font in un documento PDF è il processo che consiste nell'includere solo i glifi utilizzati nel documento, piuttosto che includere tutti i font completi. Ciò riduce le dimensioni del file PDF includendo solo i dati dei font necessari per visualizzare i caratteri effettivamente utilizzati nel documento.

#### D: Qual è la differenza tra l'incorporamento di caratteri completi e l'incorporamento di sottoinsiemi di caratteri?
R: Incorporamento completo dei caratteri significa includere tutti i caratteri utilizzati nel documento nel file PDF, il che garantisce che il documento venga visualizzato esattamente come è stato progettato, ma può aumentare le dimensioni del file PDF. Al contrario, l'incorporamento di sottoinsiemi di caratteri contiene solo i glifi utilizzati nel documento, riducendo così le dimensioni del file PDF, ma limitando la possibilità di replicare esattamente l'aspetto del documento se in seguito vengono aggiunti altri caratteri.

#### D: Come posso incorporare sottoinsiemi di caratteri in un documento PDF utilizzando Aspose.Words per .NET?
R: Per incorporare sottoinsiemi di caratteri in un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Imposta il percorso della directory del documento sostituendo`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Caricare il documento che si desidera elaborare utilizzando il file`Document` class e il percorso del documento.

 Configura le opzioni di salvataggio PDF creando un'istanza del file`PdfSaveOptions` classe e l'impostazione del`EmbedFullFonts` proprietà a`false`Ciò garantisce che nel file PDF vengano inclusi solo i sottoinsiemi di font utilizzati nel documento.

 Salva il documento in formato PDF con i sottoinsiemi di caratteri incorporati utilizzando il file`Save` metodo del`Document` oggetto, specificando il nome del file di output e le opzioni di salvataggio configurate in precedenza.

#### D: Quali sono i vantaggi dell'incorporamento di sottoinsiemi di font in un documento PDF?
R: I vantaggi dell'incorporamento di sottoinsiemi di font in un documento PDF sono:

Dimensioni ridotte del file PDF: includendo solo i glifi utilizzati nel documento, la dimensione del file PDF viene ridotta rispetto all'incorporamento di caratteri completi.

Conservazione dell'aspetto del documento: i sottoinsiemi di caratteri inclusi nel file PDF consentono di riprodurre l'aspetto del documento utilizzando solo i caratteri effettivamente utilizzati.

Compatibilità con le restrizioni della licenza: l'incorporamento di sottoinsiemi di caratteri può essere preferito nei casi in cui i caratteri completi non possono essere incorporati legalmente a causa di restrizioni di licenza.