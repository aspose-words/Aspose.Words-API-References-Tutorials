---
title: Salta i caratteri Arial e Times Roman incorporati
linktitle: Salta i caratteri Arial e Times Roman incorporati
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo-passo per generare PDF senza incorporare i caratteri Arial e Times Roman con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Questo articolo fornisce una guida dettagliata su come utilizzare la funzione per saltare i caratteri Arial e Times Roman incorporati alla dimensione del metafile con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come configurare l'opzione della modalità di incorporamento dei caratteri in un documento e generare un PDF senza incorporare i caratteri Arial e Times Roman.

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
