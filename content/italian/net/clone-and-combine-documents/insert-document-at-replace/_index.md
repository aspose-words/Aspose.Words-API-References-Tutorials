---
title: Inserisci documento in Sostituisci
linktitle: Inserisci documento in Sostituisci
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un documento in sostituzione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/clone-and-combine-documents/insert-document-at-replace/
---
In questo tutorial, ti spiegheremo come inserire un documento in un altro documento durante la sostituzione utilizzando la funzione Inserisci documento durante la sostituzione di Aspose.Words per .NET. Seguire i passaggi seguenti per comprendere il codice sorgente ed eseguire l'inserimento del documento.

## Passaggio 1: caricamento del documento principale

Per iniziare, specifica la directory per i tuoi documenti e carica il documento principale in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Passaggio 2: configura le opzioni di ricerca e sostituzione

Ora configureremo le opzioni di ricerca e sostituzione specificando la direzione di ricerca e il callback di sostituzione per inserire un documento in un altro documento. Ecco come:

```csharp
// Configura le opzioni di ricerca e sostituzione.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Passaggio 3: chiamata al metodo di sostituzione

Chiameremo ora il metodo replace per trovare e sostituire il testo specificato con una stringa vuota, utilizzando le opzioni configurate. Ecco come:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Codice sorgente di esempio per Inserisci documento in sostituzione utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Inserisci documento quando si sostituisce Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Imposta le opzioni di ricerca e sostituzione.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Chiama il metodo di sostituzione.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Conclusione

In questo tutorial, abbiamo esplorato come inserire un documento in un altro documento durante la sostituzione utilizzando la funzionalità Inserisci documento durante la sostituzione di Aspose.Words per .NET. Configurando le opzioni di ricerca e sostituzione e fornendo i dati necessari, è possibile assemblare dinamicamente i documenti sostituendo segnaposto specifici con il contenuto di altri modelli o sezioni di documento. Aspose.Words per .NET offre un modo potente e flessibile per gestire attività complesse di manipolazione di documenti, rendendolo uno strumento prezioso per automatizzare la creazione di documenti e gli scenari di inserimento di contenuti.

### Domande frequenti

#### D: Qual è lo scopo di inserire un documento in un altro documento durante la sostituzione?

R: L'inserimento di un documento in un altro documento durante la sostituzione consente di sostituire dinamicamente un segnaposto specifico con il contenuto di un documento separato. Questa funzionalità è particolarmente utile quando si desidera assemblare un documento più grande combinando vari modelli o sezioni di documento predefiniti in segnaposto specifici.

#### D: Come inserisco un documento in un altro documento durante la sostituzione utilizzando Aspose.Words per .NET?

R: Per inserire un documento in un altro documento durante la sostituzione utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:
1. Carica il documento principale che contiene i segnaposto in un oggetto Document.
2. Configura le opzioni di ricerca e sostituzione, inclusa la direzione di ricerca e la richiamata di sostituzione per gestire l'inserimento del documento.
3. Chiama il metodo replace con il pattern di ricerca appropriato, sostituendo i segnaposto con una stringa vuota, utilizzando le opzioni configurate.

#### D: Posso personalizzare il comportamento di inserimento durante la sostituzione?

R: Sì, puoi personalizzare il comportamento di inserimento durante la sostituzione implementando un ReplacingCallback personalizzato. Ereditando dall'interfaccia IReplacingCallback, puoi controllare il modo in cui i documenti vengono inseriti e uniti in base ai tuoi requisiti specifici durante la sostituzione dei segnaposto.

#### D: Posso sostituire più segnaposto con documenti diversi?

R: Sì, puoi sostituire più segnaposto con documenti diversi specificando gli schemi di ricerca appropriati per ciascun segnaposto e fornendo i corrispondenti documenti da inserire.