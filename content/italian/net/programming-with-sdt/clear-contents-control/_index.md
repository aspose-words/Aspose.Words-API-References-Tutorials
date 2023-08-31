---
title: Cancella controllo contenuto
linktitle: Cancella controllo contenuto
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come cancellare il contenuto di un controllo in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/clear-contents-control/
---

Questo tutorial mostra come cancellare il contenuto di un SDT in un documento di Word utilizzando Aspose.Words per .NET. La cancellazione del contenuto di un SDT rimuove qualsiasi testo o nodo figlio all'interno del controllo del contenuto.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e Word Processing con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e ottenere lo StructuredDocumentTag
 Carica il documento Word usando il file`Document` costruttore, passando il percorso al documento come parametro. Quindi, recupera il file desiderato`StructuredDocumentTag` dal documento. In questo esempio, assumiamo che SDT sia il primo nodo figlio nel documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Passaggio 3: cancella i contenuti di StructuredDocumentTag
 Cancellare il contenuto dell'SDT utilizzando il file`Clear` metodo. Ciò rimuove qualsiasi testo o nodo figlio all'interno del controllo del contenuto.

```csharp
sdt.Clear();
```

## Passaggio 4: salvare il documento
 Salvare il documento modificato utilizzando il file`Save`metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Esempio di codice sorgente per Clear Contents Control utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Questo è tutto! Hai cancellato correttamente il contenuto di un StructuredDocumentTag nel tuo documento Word utilizzando Aspose.Words per .NET.