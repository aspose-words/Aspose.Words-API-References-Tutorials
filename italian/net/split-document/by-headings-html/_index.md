---
title: Per titoli Html
linktitle: Per titoli Html
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per spiegare il codice sorgente C# della funzione HTML By Heading di Aspose.Words per .NET
type: docs
weight: 10
url: /it/net/split-document/by-headings-html/
---
In questo tutorial, ti illustreremo come suddividere un documento Word in parti più piccole utilizzando la funzione Intestazione HTML di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e generare documenti HTML separati basati sull'intestazione.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per il tuo documento e carica il documento in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Passaggio 2: divisione del documento per intestazione in formato HTML

Ora imposteremo le opzioni di salvataggio per dividere il documento in parti più piccole in base all'intestazione in formato HTML. Ecco come:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Dividi il documento in parti più piccole, in questo caso separandolo per titolo.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Esempio di codice sorgente per By Headings HTML utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione By HTML Heading di Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	HtmlSaveOptions options = new HtmlSaveOptions
	{
		// Dividere un documento in parti più piccole, in questo caso suddivise per intestazione.
		DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
	};
	

	doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
	

```

Con questo codice, sarai in grado di dividere un documento Word in parti più piccole usando Aspose.Words per .NET, basato su intestazioni. È quindi possibile generare documenti HTML separati per ciascuna parte.

