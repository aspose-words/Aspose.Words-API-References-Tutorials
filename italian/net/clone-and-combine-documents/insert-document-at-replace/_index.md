---
title: Inserisci documento al momento della sostituzione
linktitle: Inserisci documento al momento della sostituzione
second_title: Riferimento all'API Aspose.Words per .NET
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
//Configura le opzioni di ricerca e sostituzione.
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