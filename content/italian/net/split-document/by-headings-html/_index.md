---
title: Dividi documento Word per intestazioni Html
linktitle: Per intestazioni Html
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per spiegare il codice sorgente C# del documento split word In base alla funzionalità HTML di Aspose.Words per .NET
type: docs
weight: 10
url: /it/net/split-document/by-headings-html/
---
In questo tutorial ti spiegheremo come dividere un documento Word in parti più piccole utilizzando la funzione Per intestazione HTML di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e generare documenti HTML separati in base all'intestazione.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per il tuo documento e carica il documento in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Passaggio 2: dividere il documento per intestazione in formato HTML

Ora imposteremo le opzioni di salvataggio per dividere il documento in parti più piccole in base all'intestazione in formato HTML. Ecco come:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Dividi il documento in parti più piccole, in questo caso separandolo per titolo.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Codice sorgente di esempio per By Headings HTML utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Intestazione HTML di Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Dividi un documento in parti più piccole, in questo caso divise per intestazione.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Con questo codice sarai in grado di dividere un documento Word in parti più piccole utilizzando Aspose.Words per .NET, in base ai titoli. È quindi possibile generare documenti HTML separati per ciascuna parte.

## Conclusione

 In questo tutorial, abbiamo imparato come dividere un documento Word in parti più piccole utilizzando la funzionalità Per intestazione HTML di Aspose.Words per .NET. Specificando il`DocumentSplitCriteria` COME`HeadingParagraph` nel`HtmlSaveOptions`, siamo stati in grado di generare documenti HTML separati in base alle intestazioni presenti nel documento originale.

Dividere un documento per intestazioni può essere utile per organizzare e gestire il contenuto, soprattutto in documenti di grandi dimensioni con più sezioni. Aspose.Words per .NET fornisce una soluzione affidabile ed efficiente per gestire la suddivisione dei documenti e generare output in vari formati.

Sentiti libero di esplorare funzionalità e opzioni aggiuntive fornite da Aspose.Words per .NET per migliorare ulteriormente le capacità di elaborazione dei documenti e semplificare il flusso di lavoro.

### Domande frequenti

#### Come posso dividere un documento Word in parti più piccole in base ai titoli utilizzando Aspose.Words per .NET?

 Per dividere un documento Word in base ai titoli, è possibile utilizzare la funzione Per intestazione HTML di Aspose.Words per .NET. Segui il codice sorgente fornito e imposta il file`DocumentSplitCriteria` A`HeadingParagraph` nel`HtmlSaveOptions` oggetto. Ciò dividerà il documento in parti più piccole in ciascuna intestazione.

#### In quali formati posso dividere il documento Word?

 Il codice sorgente fornito dimostra la suddivisione del documento Word in parti più piccole in formato HTML. Tuttavia, Aspose.Words per .NET supporta vari formati di output, inclusi DOCX, PDF, EPUB e altri. È possibile modificare il codice e specificare il formato di output desiderato nel file`HtmlSaveOptions` opporsi di conseguenza.

#### Posso scegliere un criterio diverso per la suddivisione del documento?

Sì, puoi scegliere criteri diversi per dividere il documento in base alle tue esigenze. Aspose.Words per .NET fornisce diverse opzioni di criteri, come ad esempio`HeadingParagraph`, `Page`, `Section` e altro ancora. Modifica il`DocumentSplitCriteria` proprietà nel`HtmlSaveOptions` oggetto per selezionare i criteri appropriati per la suddivisione.

#### Come posso personalizzare l'HTML di output per le parti divise?

 Aspose.Words per .NET ti consente di personalizzare l'HTML di output per le parti divise specificando opzioni aggiuntive nel`HtmlSaveOptions` oggetto. Puoi controllare vari aspetti come stili CSS, immagini, caratteri e altro. Fare riferimento alla documentazione di Aspose.Words per maggiori dettagli sulla personalizzazione dell'output HTML.

#### Posso dividere il documento in base a più criteri?

 Sì, puoi dividere il documento in base a più criteri combinando di conseguenza le opzioni dei criteri. Ad esempio, puoi dividere il documento sia per intestazione che per pagina impostando il file`DocumentSplitCriteria`proprietà a`HeadingParagraph | Page`. Ciò dividerà il documento in ogni intestazione e in ogni pagina, creando parti più piccole basate su entrambi i criteri.