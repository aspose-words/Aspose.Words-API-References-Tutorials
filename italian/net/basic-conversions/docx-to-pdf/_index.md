---
title: Da Docx A Pdf
linktitle: Da Docx A Pdf
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire documenti Word da Docx a PDF utilizzando Aspose.Words per .NET. Tutorial passo passo con codice sorgente di esempio.
type: docs
weight: 10
url: /it/net/basic-conversions/docx-to-pdf/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per convertire un documento Word in formato Docx in PDF. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto con il percorso del documento di origine in formato Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Passaggio 2: salvare il documento in formato PDF

 Successivamente, salva il documento in formato PDF chiamando il file`Save` metodo sul`Document` oggetto e fornendo il percorso e il nome del file per il documento PDF di output:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

Questo è tutto! Hai convertito con successo un documento Word in formato Docx in PDF utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Docx To Pdf utilizzando Aspose.Words per .NET

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.
