---
title: Aggiungi documento
linktitle: Aggiungi documento
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiungere il contenuto di un documento a un altro utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/append-document/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per aggiungere il contenuto di un documento a un altro. Il codice sorgente fornito mostra come aprire i documenti di origine e di destinazione, importare e aggiungere sezioni dal documento di origine al documento di destinazione.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare il gestore di pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classe. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: aggiungi sezioni dal documento di origine al documento di destinazione

 Passa attraverso tutte le sezioni nel documento di origine e importa ogni sezione nel documento di destinazione utilizzando il file`ImportNode` metodo. Quindi, aggiungi la sezione importata al documento di destinazione.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Passaggio 4: salvare il documento di destinazione

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Questo completa l'implementazione dell'aggiunta di un documento utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Accoda documento utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Passa in rassegna tutte le sezioni del documento di origine.
	// I nodi di sezione sono figli immediati del nodo Documento, quindi possiamo semplicemente enumerare il Documento.
	foreach (Section srcSection in srcDoc)
	{
		// Poiché stiamo copiando una sezione da un documento a un altro,
		// è necessario importare il nodo Sezione nel documento di destinazione.
		// Questo regola eventuali riferimenti specifici del documento a stili, elenchi, ecc.
		//
		// L'importazione di un nodo crea una copia del nodo originale, ma la copia
		// è pronto per essere inserito nel documento di destinazione.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Ora il nuovo nodo di sezione può essere aggiunto al documento di destinazione.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```