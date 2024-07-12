---
title: Imposta le opzioni della nota finale
linktitle: Imposta le opzioni della nota finale
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare le opzioni delle note di chiusura nei documenti di Word utilizzando Aspose.Words per .NET. Tutorial passo passo con codice sorgente di esempio.
type: docs
weight: 10
url: /it/net/working-with-footnote-and-endnote/set-endnote-options/
---

In questo tutorial passo passo, ti guideremo su come utilizzare Aspose.Words per .NET per impostare le opzioni delle note di chiusura in un documento Word. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

 Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai già fatto, scarica e installa la libreria da[Aspose.Releases]https://releases.aspose.com/words/net/.

## Passaggio 1: inizializzazione dell'oggetto documento

 Innanzitutto, inizializza il file`Document` oggetto fornendo il percorso del documento di origine:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Passaggio 2: inizializzazione dell'oggetto DocumentBuilder

 Successivamente, inizializza il file`DocumentBuilder` oggetto per eseguire operazioni sul documento:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: aggiunta di testo e nota di chiusura

 Usa il`Write` metodo del`DocumentBuilder` oggetto per aggiungere testo al documento e il file`InsertFootnote` metodo per inserire una nota di chiusura:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Passaggio 4: impostazione delle opzioni delle note di chiusura

 Accedi al`EndnoteOptions`proprietà del documento per modificare le opzioni della nota di chiusura. In questo esempio, impostiamo la regola di riavvio per riavviare su ogni pagina e la posizione alla fine della sezione:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Passaggio 5: salvataggio del documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Questo è tutto! Hai impostato correttamente le opzioni delle note di chiusura in un documento Word utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per impostare le opzioni delle note di chiusura utilizzando Aspose.Words per .NET

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

Sentiti libero di utilizzare questo codice nei tuoi progetti e modificarlo in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso definire lo stile delle note di chiusura in Aspose.Words?

 A: Per definire lo stile delle note di chiusura in Aspose.Words, puoi utilizzare il file`EndnoteOptions` classe e il`SeparatorNoteTextStyle` proprietà. Puoi specificare lo stile del carattere, la dimensione, il colore, ecc. per le note di chiusura utilizzando questa proprietà.

#### D: È possibile personalizzare la numerazione delle note di chiusura in un documento?

 R: Sì, è possibile personalizzare la numerazione delle note di chiusura in un documento. Puoi usare il`RestartRule`E`NumberStyle` proprietà del`EndnoteOptions` classe per definire regole di riavvio e stili di numerazione specifici.

#### D: Come posso posizionare le note di chiusura in un documento?

R: Per posizionare le note di chiusura in un documento, puoi utilizzare il file`Position` proprietà del`EndnoteOptions` classe. Puoi specificare se le note di chiusura devono essere posizionate alla fine di ogni pagina, alla fine di ogni sezione o alla fine del documento.

#### D: Posso personalizzare il formato di numerazione delle note di chiusura?

 R: Sì, puoi personalizzare il formato della numerazione delle note di chiusura in Aspose.Words. Usa il`NumberFormat` proprietà del`EndnoteOptions` classe per impostare il formato desiderato, come numeri arabi, numeri romani, lettere, ecc.

#### D: È possibile continuare la numerazione delle note di chiusura tra le sezioni di un documento?

 R: Sì, è possibile continuare la numerazione delle note di chiusura tra le sezioni di un documento. Usa il`RestartRule` proprietà del`EndnoteOptions` class e impostarlo su`RestartContinuous` per consentire la numerazione di continuare tra le sezioni.