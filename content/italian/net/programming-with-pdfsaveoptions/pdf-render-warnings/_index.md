---
title: Avvertenze sul rendering del PDF
linktitle: Avvertenze sul rendering del PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per gestire gli avvisi di rendering PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzionalità di avvisi di rendering PDF con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial sarai in grado di capire come gestire gli avvisi di rendering durante la conversione in PDF.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. È possibile trovare la libreria e le istruzioni di installazione sul sito Web Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio presupponiamo che il documento si chiami "WMF con image.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Passaggio 3: configura le opzioni di salvataggio come PDF con avvisi di rendering

 Per gestire gli avvisi di rendering durante la conversione in PDF, dobbiamo configurare il file`MetafileRenderingOptions` oggetto per specificare come viene eseguito il rendering dei metafile. Usiamo anche il`HandleDocumentWarnings` opzione per gestire gli avvisi generati durante il salvataggio del documento.

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

Gli avvisi di rendering generati durante il salvataggio del documento possono essere recuperati utilizzando il gestore di avvisi personalizzato. In questo esempio, stampiamo semplicemente la descrizione di ciascun avviso.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

È tutto ! Hai gestito correttamente gli avvisi di rendering durante la conversione di un documento

  in PDF utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per avvisi di rendering PDF con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	//Se Aspose.Words non riesce a eseguire correttamente il rendering di alcuni record del metafile
	// alla grafica vettoriale, Aspose.Words esegue il rendering di questo metafile in una bitmap.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Mentre il file viene salvato correttamente, gli avvisi di rendering che si sono verificati durante il salvataggio vengono raccolti qui.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

### Domande frequenti

#### D: Qual è la funzionalità degli avvisi di rendering PDF con Aspose.Words per .NET?
La funzionalità Avvisi sul rendering PDF con Aspose.Words per .NET aiuta a gestire gli avvisi generati durante la conversione di un documento in PDF. Fornisce un modo per rilevare e gestire gli avvisi di rendering per garantire la qualità e l'integrità del documento convertito.

#### D: Come posso utilizzare questa funzionalità con Aspose.Words per .NET?
Per utilizzare questa funzionalità con Aspose.Words per .NET, attenersi alla seguente procedura:

Imposta la directory dei documenti specificando il percorso della directory in cui si trovano i tuoi documenti.

 Caricare il documento da elaborare utilizzando il file`Document` metodo e specificando il percorso del file.

 Configura le opzioni di salvataggio in PDF creando un'istanza del file`PdfSaveOptions` classe. Usa il`MetafileRenderingOptions` class per specificare come vengono visualizzati e impostati i metafile`MetafileRenderingOptions.RenderingMode` A`MetafileRenderingMode.VectorWithFallback`.

 Usa il`HandleDocumentWarnings` classe per gestire gli avvisi di rendering. Impostato`doc.WarningCallback` a un'istanza di questa classe.

 Usa il`Save` metodo per salvare il documento in formato PDF specificando le opzioni di salvataggio.

È quindi possibile gestire gli avvisi di rendering utilizzando il file`HandleDocumentWarnings` classe. Ad esempio, puoi visualizzare la descrizione di ciascun avviso utilizzando un ciclo.

#### D: Come faccio a sapere se sono presenti avvisi di rendering durante la conversione del documento in PDF?
 Puoi usare il`HandleDocumentWarnings` classe per recuperare gli avvisi di rendering generati durante il salvataggio del documento. Questa classe contiene a`mWarnings` elenco che memorizza informazioni sugli avvisi. È possibile sfogliare questo elenco e accedere alle proprietà di ciascun avviso, come la descrizione, per intraprendere l'azione appropriata.

#### D: Che tipo di avvisi di rendering possono essere generati durante la conversione in PDF?
Gli avvisi di rendering durante la conversione in PDF possono includere avvisi relativi al layout, caratteri mancanti, immagini non supportate, problemi di compatibilità, ecc. Gli avvisi specifici dipenderanno dal contenuto del documento di origine e dalle opzioni di conversione utilizzate.

#### D: È possibile gestire gli avvisi di rendering in modo personalizzato?
 Sì, puoi personalizzare la gestione degli avvisi di rendering personalizzando il file`HandleDocumentWarnings`classe. Puoi aggiungere funzionalità aggiuntive per gestire avvisi specifici per la tua applicazione, come la registrazione di avvisi, la generazione di report, l'invio di avvisi e altro ancora.