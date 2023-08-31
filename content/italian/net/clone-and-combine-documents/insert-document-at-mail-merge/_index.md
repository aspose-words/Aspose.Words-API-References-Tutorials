---
title: Inserisci documento nella stampa unione
linktitle: Inserisci documento nella stampa unione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un documento in un altro durante la stampa unione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
In questo tutorial, ti spiegheremo come inserire un documento in un altro documento durante la stampa unione utilizzando la funzione Inserisci documento durante la stampa unione di Aspose.Words per .NET. Seguire i passaggi seguenti per comprendere il codice sorgente ed eseguire l'inserimento del documento.

## Passaggio 1: caricamento del documento principale

Per iniziare, specifica la directory per i tuoi documenti e carica il documento principale in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Passaggio 2: configura la stampa unione

Ora configuriamo la stampa unione e specifichiamo il campo merge callback per inserire un documento in un altro documento. Ecco come:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Passaggio 3: esecuzione della stampa unione

Eseguiremo la stampa unione fornendo i nomi dei campi di unione e i dati corrispondenti. Ecco come:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Codice sorgente di esempio per Inserisci documento nella stampa unione utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Inserisci documento nella stampa unione di Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Il documento principale contiene un campo di unione chiamato "Documento_1".
// I dati corrispondenti per questo campo contengono un percorso completo al documento.
// Dovrebbe essere inserito in questo campo.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Con questo codice sarai in grado di inserire un documento in un altro documento durante la stampa unione utilizzando Aspose.Words per .NET. Il documento risultante verrà salvato con un nuovo nome


## Conclusione

In questo tutorial, abbiamo esplorato come inserire un documento in un altro documento durante la stampa unione utilizzando la funzionalità Inserisci documento durante la stampa unione di Aspose.Words per .NET. Configurando la stampa unione e fornendo i dati necessari, è possibile assemblare dinamicamente i documenti unendo vari modelli o sezioni di documento. Aspose.Words per .NET fornisce un modo flessibile e potente per gestire scenari complessi di generazione di documenti, rendendolo uno strumento prezioso per automatizzare le attività di creazione e manipolazione di documenti.

### Domande frequenti

#### D: Qual è lo scopo di inserire un documento in un altro documento durante la stampa unione?

R: L'inserimento di un documento in un altro documento durante la stampa unione consente di combinare diversi modelli o sezioni di documento in modo dinamico in base ai dati forniti durante il processo di unione. Questa funzionalità è particolarmente utile quando si desidera assemblare documenti complessi unendo vari modelli o sezioni predefiniti in un documento finale.

#### D: Come posso inserire un documento in un altro documento durante la stampa unione utilizzando Aspose.Words per .NET?

R: Per inserire un documento in un altro documento durante la stampa unione utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:
1. Carica il documento principale che fungerà da base in un oggetto Document.
2. Configurare la stampa unione e specificare il callback dell'unione dei campi per gestire l'inserimento del documento.
3. Esegui la stampa unione con i nomi dei campi unione e i dati corrispondenti (percorso del documento da inserire).

#### D: Come posso personalizzare il comportamento di inserimento durante la stampa unione?

R: Per personalizzare il comportamento di inserimento durante la stampa unione, è possibile implementare un FieldMergingCallback personalizzato ereditandolo dall'interfaccia IFieldMergingCallback. Ciò ti consente di controllare il modo in cui i documenti vengono inseriti e uniti in base ai tuoi requisiti specifici.

#### D: Posso inserire più documenti durante la stampa unione?

R: Sì, puoi inserire più documenti durante la stampa unione fornendo i dati appropriati per ciascun campo unione. Per ogni campo di unione che richiede l'inserimento di documenti, specificare il percorso del documento corrispondente come dati.


