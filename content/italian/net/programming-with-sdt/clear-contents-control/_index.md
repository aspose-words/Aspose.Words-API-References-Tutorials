---
title: Cancella controllo dei contenuti
linktitle: Cancella controllo dei contenuti
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come cancellare il contenuto di un controllo in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/clear-contents-control/
---

Questo tutorial dimostra come cancellare il contenuto di un SDT in un documento Word utilizzando Aspose.Words per .NET. La cancellazione del contenuto di un SDT rimuove qualsiasi testo o nodo figlio all'interno del controllo contenuto.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e ottenere StructuredDocumentTag
 Caricare il documento Word utilizzando il file`Document` costruttore, passando il percorso del documento come parametro. Quindi, recupera il desiderato`StructuredDocumentTag`dal documento. In questo esempio, presupponiamo che SDT sia il primo nodo figlio nel documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Passaggio 3: cancellare il contenuto di StructuredDocumentTag
 Cancellare il contenuto dell'SDT utilizzando il file`Clear` metodo. Ciò rimuove qualsiasi testo o nodo figlio all'interno del controllo contenuto.

```csharp
sdt.Clear();
```

## Passaggio 4: salva il documento
 Salvare il documento modificato utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Codice sorgente di esempio per Clear Contents Control utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Questo è tutto! Hai cancellato con successo il contenuto di un StructuredDocumentTag nel tuo documento Word utilizzando Aspose.Words per .NET.