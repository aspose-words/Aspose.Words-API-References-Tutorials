---
title: Carica intervallo di pagine del PDF
linktitle: Carica intervallo di pagine del PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per caricare un intervallo di pagine PDF specifico con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

In questo tutorial ti spiegheremo come caricare un intervallo di pagine specifico da un documento PDF utilizzando Aspose.Words per .NET. Seguire i passaggi seguenti:

## Passaggio 1: caricamento di un intervallo di pagine PDF

Utilizzare il codice seguente per caricare un intervallo di pagine specifico da un documento PDF:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 In questo esempio, stiamo caricando la prima pagina del documento PDF. Puoi modificare i valori di`PageIndex` E`PageCount` all'intervallo di pagine desiderato.

## Passaggio 2: salvataggio del documento

 Infine, puoi salvare il documento contenente l'intervallo di pagine specifico utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Assicurati di specificare il percorso corretto per salvare il documento modificato.

È tutto ! Ora hai caricato un intervallo di pagine specifico da un documento PDF utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Carica intervallo di pagine di Pdf utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Ricordati di specificare il percorso corretto della directory dei tuoi documenti PDF.



