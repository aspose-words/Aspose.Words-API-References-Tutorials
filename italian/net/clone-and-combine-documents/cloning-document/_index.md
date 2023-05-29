---
title: Documento di clonazione
linktitle: Documento di clonazione
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come clonare un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/clone-and-combine-documents/cloning-document/
---

In questo tutorial, ti spiegheremo come clonare un documento Word usando la funzione clone di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e creare una copia esatta di un documento esistente.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory del documento e carica il documento esistente in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Passaggio 2: clonare il documento

Ora andremo a clonare il documento creandone una copia esatta. Ecco come:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Esempio di codice sorgente per la clonazione di un documento utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione di clonazione del documento Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

Con questo codice sarai in grado di clonare un documento Word usando Aspose.Words per .NET. La copia esatta del documento verrà salvata con un nuovo nome file.

