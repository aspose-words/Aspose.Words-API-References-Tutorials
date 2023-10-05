---
title: Imposta la posizione della nota a piè di pagina e della nota finale
linktitle: Imposta la posizione della nota a piè di pagina e della nota finale
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare la posizione delle note a piè di pagina e delle note di chiusura nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

In questo tutorial passo passo, ti guideremo su come utilizzare Aspose.Words per .NET per impostare la posizione delle note a piè di pagina e delle note di chiusura in un documento Word. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

 Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non lo hai già fatto, scarica e installa la libreria da[Aspose.Releases]https://releases.aspose.com/words/net/.

## Passaggio 1: inizializzazione dell'oggetto documento

 Innanzitutto, inizializza il file`Document` oggetto fornendo il percorso del documento di origine:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Passaggio 2: impostazione della posizione della nota a piè di pagina e della nota di chiusura

 Successivamente, accedi a`FootnoteOptions` E`EndnoteOptions` proprietà del documento per impostare la posizione delle note a piè di pagina e delle note di chiusura. In questo esempio, impostiamo la posizione delle note a piè di pagina sotto il testo e la posizione delle note di chiusura alla fine della sezione:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Passaggio 3: salvataggio del documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Questo è tutto! Hai impostato con successo la posizione delle note a piè di pagina e delle note di chiusura in un documento di Word utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per impostare la posizione della nota a piè di pagina e della nota finale utilizzando Aspose.Words per .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e modificarlo in base alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso posizionare le note a piè di pagina e le note di chiusura in Aspose.Words?

 R: Per posizionare le note a piè di pagina e le note di chiusura in Aspose.Words, è necessario utilizzare il file`FootnoteOptions` classe e il`Position` proprietà. Puoi impostare questa proprietà su qualsiasi valore tu voglia, ad esempio`BottomOfPage` (in fondo alla pagina) oppure`EndOfSection` (alla fine della sezione).

#### D: È possibile personalizzare la posizione delle note a piè di pagina e di chiusura per ogni pagina o sezione del documento?

R: Sì, è possibile personalizzare la posizione delle note a piè di pagina e delle note di chiusura per ogni pagina o sezione del documento. È possibile utilizzare la sezione Aspose.Words e i metodi di manipolazione della pagina per definire posizioni specifiche per le note a piè di pagina e le note di chiusura.

#### D: Come posso rimuovere le note a piè di pagina o le note di chiusura da un documento?

 A: Per rimuovere note a piè di pagina o note di chiusura da un documento in Aspose.Words, è possibile utilizzare metodi appropriati come`RemoveAllFootnotes` per rimuovere tutte le note a piè di pagina o`RemoveAllEndnotes` per rimuovere tutte le note di chiusura. Assicurati di salvare il documento dopo aver eseguito queste operazioni.

#### D: Le note a piè di pagina e le note di chiusura possono essere posizionate fuori dai margini della pagina?

No, per impostazione predefinita le note a piè di pagina e le note di chiusura non possono essere posizionate all'esterno dei margini della pagina in Aspose.Words. Tuttavia, puoi regolare i margini del documento per lasciare più spazio per le note a piè di pagina e di chiusura, se necessario.

#### D: È possibile personalizzare le note a piè di pagina e le note di chiusura con caratteri o stili di formattazione specifici?

R: Sì, puoi personalizzare le note a piè di pagina e le note di chiusura con caratteri specifici o stili di formattazione in Aspose.Words. È possibile utilizzare i metodi e le proprietà disponibili per applicare stili di carattere, colori, dimensioni dei caratteri, ecc. Note a piè di pagina e note di chiusura.