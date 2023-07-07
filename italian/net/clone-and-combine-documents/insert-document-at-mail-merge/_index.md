---
title: Inserisci documento alla stampa unione
linktitle: Inserisci documento alla stampa unione
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un documento in un altro durante la stampa unione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/clone-and-combine-documents/insert-document-at-mail-merge/
---

In questo tutorial, ti illustreremo come inserire un documento in un altro documento durante la stampa unione utilizzando la funzione Inserisci documento durante la stampa unione di Aspose.Words per .NET. Seguire i passaggi seguenti per comprendere il codice sorgente ed eseguire l'inserimento del documento.

## Passaggio 1: caricamento del documento principale

Per iniziare, specifica la directory per i tuoi documenti e carica il documento principale in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Passaggio 2: configurare la stampa unione

Ora configuriamo la stampa unione e specifichiamo il campo merge callback per inserire un documento in un altro documento. Ecco come:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Passaggio 3: eseguire la stampa unione

Eseguiremo la stampa unione fornendo i nomi dei campi di unione ei dati corrispondenti. Ecco come:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Esempio di codice sorgente per Inserisci documento alla stampa unione utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Inserisci documento nella stampa unione di Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Il documento principale contiene un campo di unione denominato "Documento_1".
// I dati corrispondenti per questo campo contengono un percorso completo del documento.
// Questo dovrebbe essere inserito in questo campo.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Con questo codice sarai in grado di inserire un documento in un altro documento durante la stampa unione utilizzando Aspose.Words per .NET. Il documento risultante verrà salvato con un nuovo nome



