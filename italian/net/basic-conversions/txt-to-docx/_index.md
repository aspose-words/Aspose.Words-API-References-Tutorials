---
title: Testo a Docx
linktitle: Testo a Docx
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire file di testo semplice (Txt) in documenti Word (Docx) utilizzando Aspose.Words per .NET. Tutorial passo passo con codice di esempio.
type: docs
weight: 10
url: /it/net/basic-conversions/txt-to-docx/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per convertire un file di testo semplice (Txt) in un documento Word in formato Docx. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto fornendo il percorso del file di testo normale:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## Passaggio 2: salvare il documento in formato Docx

 Successivamente, salva il documento nel formato Docx chiamando il file`Save` metodo sul`Document`oggetto e fornendo il percorso e il nome del file per il documento Docx di output:

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

Questo è tutto! Hai convertito con successo un file di testo semplice (Txt) in un documento Word in formato Docx utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Txt To Docx utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// La codifica del file di testo viene rilevata automaticamente.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.