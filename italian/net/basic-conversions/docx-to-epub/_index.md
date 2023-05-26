---
title: Docx in Epub
linktitle: Docx in Epub
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire i documenti Word dal formato Docx al formato Epub utilizzando Aspose.Words per .NET. Tutorial passo passo con codice sorgente di esempio.
type: docs
weight: 10
url: /it/net/basic-conversions/docx-to-epub/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per convertire un documento Word in formato Docx nel formato Epub. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Innanzitutto, è necessario inizializzare il file`Document` oggetto fornendo il percorso del documento di origine in formato Docx. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento e`"Document.docx"` con il nome del documento di origine. Ecco lo snippet di codice:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Passaggio 2: conversione del documento in formato Epub

 Successivamente, puoi procedere con il processo di conversione. Chiama il`Save` metodo sul`Document` oggetto e fornire il percorso e il nome del file per il documento di output in formato Epub. In questo esempio, lo salveremo come`"BaseConversions.DocxToEpub.epub"`. Ecco lo snippet di codice:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

Questo è tutto! Hai convertito con successo un documento Word in formato Docx nel formato Epub utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Docx To Epub utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.