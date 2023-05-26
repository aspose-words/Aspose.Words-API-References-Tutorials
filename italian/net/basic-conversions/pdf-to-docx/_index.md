---
title: Da PDF a Docx
linktitle: Da PDF a Docx
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire documenti PDF in formato Docx utilizzando Aspose.Words per .NET. Tutorial passo passo con codice sorgente di esempio.
type: docs
weight: 10
url: /it/net/basic-conversions/pdf-to-docx/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per convertire un documento PDF nel formato Docx. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto fornendo il percorso del documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Passaggio 2: salvare il documento in formato Docx

 Successivamente, salva il documento nel formato Docx chiamando il file`Save` metodo sul`Document`oggetto e fornendo il percorso e il nome del file per il documento Docx di output:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
```

Questo è tutto! Hai convertito con successo un documento PDF nel formato Docx utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Pdf To Docx utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
	
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.