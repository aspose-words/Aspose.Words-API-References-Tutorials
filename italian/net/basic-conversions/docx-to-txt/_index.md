---
title: Docx in testo
linktitle: Docx in testo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire documenti Word da Docx a testo normale (Txt) utilizzando Aspose.Words per .NET. Tutorial passo passo con codice sorgente di esempio.
type: docs
weight: 10
url: /it/net/basic-conversions/docx-to-txt/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per convertire un documento Word in formato Docx in testo normale (Txt). Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto con il percorso del documento di origine in formato Docx:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Passaggio 2: salvare il documento in formato Txt

 Successivamente, salva il documento in formato testo normale (Txt) chiamando il file`Save` metodo sul`Document` oggetto e fornendo il percorso e il nome del file per il documento Txt di output:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");
```

Questo è tutto! Hai convertito con successo un documento Word in formato Docx in testo normale (Txt) utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Docx To Txt utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");

```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.