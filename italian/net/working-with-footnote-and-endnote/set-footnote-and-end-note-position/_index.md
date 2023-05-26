---
title: Imposta la posizione della nota a piè di pagina e della nota finale
linktitle: Imposta la posizione della nota a piè di pagina e della nota finale
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare la posizione delle note a piè di pagina e di chiusura nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per impostare la posizione delle note a piè di pagina e delle note di chiusura in un documento di Word. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto fornendo il percorso del documento di origine:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Passaggio 2: impostazione della posizione delle note a piè di pagina e di chiusura

 Successivamente, accedi al file`FootnoteOptions` E`EndnoteOptions`proprietà del documento per impostare la posizione delle note a piè di pagina e di chiusura. In questo esempio, impostiamo la posizione delle note a piè di pagina sotto il testo e la posizione delle note di chiusura alla fine della sezione:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Passaggio 3: salvare il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Questo è tutto! Hai impostato correttamente la posizione delle note a piè di pagina e di chiusura in un documento di Word utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Imposta posizione nota a piè di pagina e nota di chiusura utilizzando Aspose.Words per .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.
