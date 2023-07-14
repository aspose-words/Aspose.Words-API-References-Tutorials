---
title: Esporta i segnalibri del piè di pagina dell'intestazione del documento Word in un documento PDF
linktitle: Esporta i segnalibri del piè di pagina dell'intestazione del documento Word in un documento PDF
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida passo passo per esportare i segnalibri del piè di pagina dell'intestazione del documento word nei segnalibri del documento pdf con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Questo articolo fornisce una guida dettagliata su come esportare i segnalibri del piè di pagina dell'intestazione del documento word nella funzionalità del documento pdf con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come esportare segnalibri da intestazioni e piè di pagina di un documento e generare un PDF con i segnalibri appropriati.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento

Successivamente, dobbiamo caricare il documento che vogliamo elaborare. In questo esempio, supponiamo che il documento si chiami "Segnalibri nelle intestazioni e nei piè di pagina.docx" e si trovi nella directory dei documenti specificata.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Passaggio 3: configurare le opzioni di salvataggio come PDF

 Per esportare i segnalibri di intestazione e piè di pagina, dobbiamo configurare il file`PdfSaveOptions` oggetto. In questo esempio, impostiamo il livello di struttura del segnalibro predefinito su 1 e la modalità di esportazione dei segnalibri di intestazione e piè di pagina su "Primo".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Passaggio 4: salva il documento come PDF con i segnalibri di intestazioni e piè di pagina

Infine, possiamo salvare il documento in formato PDF utilizzando le opzioni di salvataggio configurate in precedenza.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

È tutto ! Hai esportato correttamente i segnalibri di intestazione e piè di pagina da un documento e hai generato un PDF con i segnalibri appropriati utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per l'esportazione di segnalibri di intestazione e piè di pagina con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Conclusione

In questo tutorial, abbiamo spiegato come esportare i segnalibri di intestazione e piè di pagina da un documento Word a un documento PDF utilizzando Aspose.Words per .NET. I segnalibri esportati consentono una facile navigazione e un rapido riferimento alle intestazioni e ai piè di pagina corrispondenti nel documento PDF generato. Segui i passaggi descritti per esportare i segnalibri di intestazione e piè di pagina da un documento e generare un PDF con i segnalibri appropriati utilizzando Aspose.Words per .NET. Assicurati di specificare il percorso corretto per i tuoi documenti e configura le opzioni di salvataggio secondo necessità.

# Domande frequenti

### D: Cosa significa esportare i segnalibri di intestazione e piè di pagina da un documento Word a un documento PDF?
R: L'esportazione di segnalibri di intestazione e piè di pagina da un documento Word a un documento PDF è una funzione per mantenere e generare segnalibri nel documento PDF dalle intestazioni e dai piè di pagina. piè di pagina del documento Word originale. Ciò consente agli utenti di navigare rapidamente e facilmente attraverso il documento PDF utilizzando i segnalibri corrispondenti a intestazioni e piè di pagina.

### D: Come posso utilizzare Aspose.Words per .NET per esportare i segnalibri di intestazione e piè di pagina da un documento Word a un documento PDF?
R: Per esportare i segnalibri di intestazione e piè di pagina da un documento Word a un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Caricare il documento che si desidera elaborare utilizzando il file`Document` class e specificare il percorso del documento Word nella directory dei documenti specificata.

 Configura le opzioni di salvataggio come PDF creando un'istanza del file`PdfSaveOptions` class e impostando le opzioni appropriate per i segnalibri di intestazione e piè di pagina.

 Salvare il documento in formato PDF utilizzando il file`Save` metodo del`Document`class specificando il percorso e le opzioni di salvataggio.

### D: Quali sono i vantaggi dell'esportazione dei segnalibri di intestazione e piè di pagina in un documento PDF?
R: I vantaggi dell'esportazione dei segnalibri di intestazione e piè di pagina in un documento PDF sono:

Navigazione semplice: i segnalibri consentono agli utenti di navigare facilmente in un documento PDF facendo riferimento a intestazioni e piè di pagina specifici.

Riferimento rapido: i segnalibri consentono agli utenti di trovare rapidamente le sezioni pertinenti del documento PDF in base a intestazioni e piè di pagina.