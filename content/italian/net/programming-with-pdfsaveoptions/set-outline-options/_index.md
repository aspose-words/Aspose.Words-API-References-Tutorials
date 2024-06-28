---
title: Imposta le opzioni del contorno in un documento PDF
linktitle: Imposta le opzioni del contorno in un documento PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per impostare le opzioni di struttura in un documento PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/set-outline-options/
---

Questo articolo fornisce una guida passo passo su come utilizzare le opzioni di struttura impostate per la funzionalità di dimensione del metafile con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial sarai in grado di capire come impostare le opzioni di contorno in un documento e generare un PDF con le opzioni di contorno corrispondenti.

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

## Passaggio 3: configura le opzioni di salvataggio come PDF con le opzioni del piano

Per impostare le opzioni di struttura nel PDF generato, dobbiamo configurare il file`PdfSaveOptions` oggetto. Possiamo impostare il numero di livelli di struttura dell'intestazione (`HeadingsOutlineLevels`) e il numero di livelli di struttura espansi (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Passaggio 4: salva il documento come PDF con le opzioni di contorno

Infine, possiamo salvare il documento in formato PDF utilizzando le opzioni di salvataggio configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

È tutto ! Hai impostato con successo le opzioni di struttura in un documento e generato un PDF con le opzioni di struttura corrispondenti utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per impostare le opzioni del piano sulla dimensione del metafile con Aspose.Words per .NET


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Conclusione

In questo tutorial, abbiamo spiegato come impostare le opzioni di struttura in un documento PDF utilizzando Aspose.Words per .NET. Utilizzando i passaggi descritti, puoi facilmente specificare i livelli di intestazione e struttura nel documento e generare un file PDF con le opzioni di struttura corrispondenti. Goditi i vantaggi dell'opzione di struttura per migliorare la struttura e la navigazione nei tuoi documenti PDF utilizzando Aspose.Words per .NET.

### Domande frequenti

#### D: Qual è l'opzione di struttura in un documento PDF?
R: L'opzione di struttura in un documento PDF si riferisce alla struttura gerarchica del contenuto del documento. Permette di creare un sommario interattivo e facilita la navigazione nel documento. Le opzioni della struttura determinano i livelli del titolo e del sottotitolo da includere nella struttura e il livello di dettaglio da visualizzare nella struttura generata.

#### D: Come posso impostare le opzioni di struttura in un documento PDF utilizzando Aspose.Words per .NET?
R: Per impostare le opzioni di struttura in un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Carica il documento che desideri convertire in PDF utilizzando il file`Document` class e specificare il percorso del documento nella directory dei documenti specificata.

 Configura le opzioni di salvataggio come PDF creando un'istanza del file`PdfSaveOptions` classe e utilizzando il file`OutlineOptions` proprietà per impostare le opzioni del contorno. È possibile specificare il numero di livelli di intestazione da includere nella struttura utilizzando il comando`HeadingsOutlineLevels` proprietà e il numero di livelli di struttura espansi utilizzando il comando`ExpandedOutlineLevels` proprietà.

 Salvare il documento in formato PDF utilizzando il file`Save` metodo del`Document` classe specificando il percorso e le opzioni di salvataggio.

#### D: Qual è l'opzione del piano in un documento PDF?
R: L'opzione di struttura in un documento PDF ti consente di creare una struttura gerarchica del contenuto, che semplifica la navigazione nel documento e l'accesso alle diverse sezioni. Ciò consente agli utenti di passare rapidamente a parti specifiche del documento facendo clic sulle voci nel sommario o nella struttura. L'opzione struttura migliora inoltre l'esperienza di lettura fornendo una panoramica della struttura complessiva del documento.
