---
title: Esporta la struttura del documento Word in un documento PDF
linktitle: Esporta la struttura del documento Word in un documento PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per esportare la struttura del documento Word in un documento PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/export-document-structure/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzione Esporta struttura del documento Word in documento PDF con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Al termine di questo tutorial sarai in grado di capire come esportare la struttura di un documento e generare un PDF con la struttura del documento visibile.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. È possibile trovare la libreria e le istruzioni di installazione sul sito Web Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio presupponiamo che il documento si chiami "Paragraphs.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Passaggio 3: configura le opzioni di salvataggio come PDF

 Per esportare la struttura del documento e rendere visibile la struttura nel riquadro di navigazione "Contenuto" di Adobe Acrobat Pro durante la modifica del file PDF, dobbiamo configurare il`PdfSaveOptions` oggetto con il`ExportDocumentStructure` proprietà impostata su`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Passaggio 4: salva il documento come PDF con la struttura del documento

Infine, possiamo salvare il documento in formato PDF utilizzando le opzioni di salvataggio configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

È tutto ! Hai esportato con successo una struttura del documento e generato un PDF con la struttura del documento visibile utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per esportare la struttura del documento con Aspose.Words per .NET


```csharp

            // Il percorso della directory dei documenti.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // La dimensione del file verrà aumentata e la struttura sarà visibile nel riquadro di navigazione "Contenuto".
            // di Adobe Acrobat Pro, durante la modifica del file .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Conclusione

In questo tutorial, abbiamo spiegato come esportare la struttura di un documento Word in un documento PDF utilizzando Aspose.Words per .NET. Seguendo i passaggi descritti, puoi generare facilmente un PDF con la struttura del documento visibile, semplificando la navigazione e la ricerca nel documento. Utilizza le funzionalità di Aspose.Words per .NET per esportare la struttura dei tuoi documenti Word e creare PDF ben strutturati.

### Domande frequenti

#### D: Che cosa significa esportare la struttura di un documento Word in un documento PDF?
R: L'esportazione della struttura di un documento Word in un documento PDF crea un PDF con una struttura del documento visibile. La struttura del documento solitamente include elementi come intestazioni, sezioni, paragrafi e altri elementi strutturati del documento. Questa struttura può essere utile per la navigazione e la ricerca nel documento PDF.

#### D: Come posso esportare la struttura di un documento Word in un documento PDF utilizzando Aspose.Words per .NET?
R: Per esportare la struttura di un documento Word in un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Crea un'istanza di`Document` classe specificando il percorso del documento Word.

 Crea un'istanza di`PdfSaveOptions`classe e impostare il file`ExportDocumentStructure` proprietà a`true`. Ciò esporterà la struttura del documento e la renderà visibile nel riquadro di navigazione "Contenuto" di Adobe Acrobat Pro durante la modifica del file PDF.

 Usa il`Save` metodo del`Document`classe per salvare il documento in formato PDF specificando le opzioni di salvataggio.

#### D: Come posso visualizzare la struttura di un documento PDF con Adobe Acrobat Pro?
R: Per visualizzare la struttura di un documento PDF con Adobe Acrobat Pro, procedi nel seguente modo:

Apri il documento PDF in Adobe Acrobat Pro.

Nella barra di navigazione sinistra, fare clic sull'icona "Contenuto" per visualizzare il riquadro di navigazione "Contenuto".

Nel riquadro di navigazione "Contenuto" vedrai la struttura del documento con intestazioni, sezioni e altri elementi strutturati.