---
title: Sostituisci il testo nel piè di pagina
linktitle: Sostituisci il testo nel piè di pagina
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come sostituire il testo nel piè di pagina dei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/replace-text-in-footer/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Sostituisci testo nel piè di pagina nella libreria Aspose.Words per .NET. Questa funzione consente di trovare e sostituire testo specifico nei piè di pagina dei documenti di Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: caricare il documento

Prima di iniziare a utilizzare la sostituzione del testo nel piè di pagina, dobbiamo caricare il documento in Aspose.Words per .NET. Questo può essere fatto usando il`Document` class e specificando il percorso del file del documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## Passaggio 2: accedi al piè di pagina

 Una volta caricato il documento, dobbiamo accedere al piè di pagina per eseguire la sostituzione del testo. Nel nostro esempio, usiamo il`HeadersFooters` proprietà della prima sezione del documento per ottenere la raccolta di intestazioni/piè di pagina. Successivamente, selezioniamo il piè di pagina principale utilizzando il file`HeaderFooterType.FooterPrimary` indice:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## Passaggio 3: configurare le opzioni di ricerca e sostituzione

 Ora configureremo le opzioni di ricerca e sostituzione utilizzando a`FindReplaceOptions` oggetto. Nel nostro esempio, impostiamo`MatchCase` A`false` per ignorare maiuscole e minuscole durante la ricerca e`FindWholeWordsOnly` A`false` per consentire la ricerca e la sostituzione di parti di parole:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## Passaggio 4: sostituisci il testo nel piè di pagina

 Noi usiamo il`Range.Replace` metodo per eseguire la sostituzione del testo nel piè di pagina. Nel nostro esempio, sostituiamo la frase "(C) 2006 Aspose Pty Ltd." da "Copyright (C) 2020 di Aspose Pty Ltd." :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## Passaggio 5: salvare il documento modificato

 Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### Esempio di codice sorgente per Sostituisci testo nel piè di pagina utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso della sostituzione del testo del piè di pagina con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Sostituisci testo nel piè di pagina di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per caricare un documento, accedere al piè di pagina, configurare le opzioni di ricerca e sostituzione, eseguire la sostituzione del testo e salvare il documento modificato.
