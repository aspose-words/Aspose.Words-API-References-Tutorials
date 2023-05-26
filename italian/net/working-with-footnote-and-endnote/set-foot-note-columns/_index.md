---
title: Imposta le colonne delle note a piè di pagina
linktitle: Imposta le colonne delle note a piè di pagina
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare il numero di colonne per le note a piè di pagina nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-footnote-and-endnote/set-foot-note-columns/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per impostare il numero di colonne per le note a piè di pagina in un documento di Word. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto fornendo il percorso del documento di origine:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Passaggio 2: impostazione delle colonne delle note a piè di pagina

 Successivamente, accedi al file`FootnoteOptions`proprietà del documento e impostare il file`Columns` proprietà per specificare il numero di colonne per le note a piè di pagina. In questo esempio, lo impostiamo su 3 colonne:

```csharp
doc.FootnoteOptions.Columns = 3;
```

## Passaggio 3: salvare il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Questo è tutto! Hai impostato correttamente il numero di colonne per le note a piè di pagina in un documento di Word utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per impostare le colonne delle note a piè di pagina utilizzando Aspose.Words per .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

// Specificare il numero di colonne con cui viene formattata l'area delle note a piè di pagina.
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.