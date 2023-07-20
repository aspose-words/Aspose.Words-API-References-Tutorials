---
title: Inserisci documento al momento della sostituzione
linktitle: Inserisci documento al momento della sostituzione
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire un documento in sostituzione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/clone-and-combine-documents/insert-document-at-replace/
---
In questo tutorial, ti illustreremo come inserire un documento in un altro documento durante la sostituzione utilizzando la funzione Inserisci documento durante la sostituzione di Aspose.Words per .NET. Seguire i passaggi seguenti per comprendere il codice sorgente ed eseguire l'inserimento del documento.

## Passaggio 1: caricamento del documento principale

Per iniziare, specifica la directory per i tuoi documenti e carica il documento principale in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Passaggio 2: configurare le opzioni di ricerca e sostituzione

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

### Esempio di codice sorgente per Insert Document At Replace utilizzando Aspose.Words per .NET

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

In questo tutorial, abbiamo esplorato come inserire un documento in un altro documento durante la sostituzione utilizzando la funzione Inserisci documento durante la sostituzione di Aspose.Words per .NET. Configurando le opzioni di ricerca e sostituzione e fornendo i dati necessari, è possibile assemblare dinamicamente i documenti sostituendo specifici segnaposto con i contenuti di altri modelli o sezioni di documenti. Aspose.Words per .NET offre un modo potente e flessibile per gestire complesse attività di manipolazione dei documenti, rendendolo uno strumento prezioso per automatizzare la creazione di documenti e scenari di inserimento di contenuti.

### FAQ

#### D: Qual è lo scopo dell'inserimento di un documento in un altro documento durante la sostituzione?

R: L'inserimento di un documento in un altro documento durante la sostituzione consente di sostituire dinamicamente un segnaposto specifico con il contenuto di un documento separato. Questa funzione è particolarmente utile quando si desidera assemblare un documento più grande combinando vari modelli o sezioni di documenti predefiniti in segnaposti specifici.

#### D: Come inserisco un documento in un altro documento durante la sostituzione utilizzando Aspose.Words per .NET?

R: Per inserire un documento in un altro documento durante la sostituzione utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:
1. Carica il documento principale che contiene i segnaposto in un oggetto Document.
2. Configura le opzioni di ricerca e sostituzione, inclusa la direzione di ricerca e sostituisci il callback per gestire l'inserimento del documento.
3. Chiamare il metodo replace con il modello di ricerca appropriato, sostituendo i segnaposto con una stringa vuota, usando le opzioni configurate.

#### D: Posso personalizzare il comportamento di inserimento durante la sostituzione?

R: Sì, puoi personalizzare il comportamento di inserimento durante la sostituzione implementando un ReplacingCallback personalizzato. Ereditando dall'interfaccia IReplacingCallback, puoi controllare come i documenti vengono inseriti e uniti in base ai tuoi requisiti specifici durante la sostituzione dei segnaposto.

#### D: Posso sostituire più segnaposto con documenti diversi?

R: Sì, puoi sostituire più segnaposto con documenti diversi specificando i modelli di ricerca appropriati per ogni segnaposto e fornendo i documenti corrispondenti da inserire.