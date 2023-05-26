---
title: Imposta le opzioni del contorno
linktitle: Imposta le opzioni del contorno
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per impostare le opzioni di contorno in un documento PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/set-outline-options/
---

Questo articolo fornisce una guida dettagliata su come utilizzare le opzioni di contorno impostate per la funzione di dimensione del metafile con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come impostare le opzioni di contorno in un documento e generare un PDF con le opzioni di contorno corrispondenti.

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

## Passaggio 3: configurare le opzioni di salvataggio come PDF con le opzioni del piano

 Per impostare le opzioni di contorno nel PDF generato, dobbiamo configurare il file`PdfSaveOptions` oggetto. Possiamo impostare il numero di livelli di struttura dell'intestazione (`HeadingsOutlineLevels`) e il numero di livelli struttura espansi (`ExpandedOutlineLevels`).

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

È tutto ! Hai impostato correttamente le opzioni di struttura in un documento e generato un PDF con le opzioni di struttura corrispondenti utilizzando Aspose.Words per .NET.

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
