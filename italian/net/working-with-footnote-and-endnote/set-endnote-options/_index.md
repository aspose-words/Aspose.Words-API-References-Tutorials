---
title: Imposta le opzioni della nota di chiusura
linktitle: Imposta le opzioni della nota di chiusura
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare le opzioni delle note di chiusura nei documenti di Word utilizzando Aspose.Words per .NET. Tutorial passo passo con codice sorgente di esempio.
type: docs
weight: 10
url: /it/net/working-with-footnote-and-endnote/set-endnote-options/
---

In questo tutorial passo-passo, ti guideremo su come utilizzare Aspose.Words per .NET per impostare le opzioni delle note di chiusura in un documento di Word. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto fornendo il percorso del documento di origine:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Passaggio 2: inizializzazione dell'oggetto DocumentBuilder

 Successivamente, inizializza il file`DocumentBuilder` opporsi all'esecuzione di operazioni sul documento:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: aggiunta di testo e nota di chiusura

 Usa il`Write` metodo del`DocumentBuilder` oggetto per aggiungere testo al documento e il`InsertFootnote` metodo per inserire una nota di chiusura:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Passaggio 4: impostazione delle opzioni della nota di chiusura

 Accedi al`EndnoteOptions` proprietà del documento per modificare le opzioni delle note di chiusura. In questo esempio, impostiamo la regola di riavvio per riavviare su ogni pagina e la posizione alla fine della sezione:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Passaggio 5: salvare il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Questo è tutto! Hai impostato correttamente le opzioni delle note di chiusura in un documento di Word utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Set Endnote Options utilizzando Aspose.Words per .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.
