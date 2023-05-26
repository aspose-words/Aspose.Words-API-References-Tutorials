---
title: Pdf Render Avvertenze
linktitle: Pdf Render Avvertenze
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per gestire gli avvisi di rendering PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzione di avviso di rendering PDF con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come gestire gli avvisi di rendering durante la conversione in PDF.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio, supponiamo che il documento si chiami "WMF con image.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Passaggio 3: configurare le opzioni di salvataggio come PDF con avvisi di rendering

Per gestire gli avvisi di rendering durante la conversione in PDF, dobbiamo configurare il file`MetafileRenderingOptions` oggetto per specificare come vengono visualizzati i metafile. Usiamo anche il`HandleDocumentWarnings` opzione per gestire gli avvisi generati durante il salvataggio del documento.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Passaggio 4: salva il documento come PDF con avvisi di rendering

Infine, possiamo salvare il documento in formato PDF utilizzando le opzioni di salvataggio configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Passaggio 5: gestire gli avvisi di rendering

Gli avvisi di rendering generati durante il salvataggio del documento possono essere recuperati utilizzando il gestore di avvisi personalizzato. In questo esempio, viene semplicemente stampata la descrizione di ciascun avviso.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

È tutto ! Hai gestito correttamente gli avvisi di rendering durante la conversione di un documento

  in PDF utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per avvisi di rendering PDF con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	// Se Aspose.Words non è in grado di eseguire correttamente il rendering di alcuni dei record del metafile
	// alla grafica vettoriale, Aspose.Words esegue il rendering di questo metafile in una bitmap.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Mentre il file viene salvato correttamente, qui vengono raccolti gli avvisi di rendering che si sono verificati durante il salvataggio.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```
