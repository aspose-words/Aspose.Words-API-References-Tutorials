---
title: Aggiungi documento allo spazio vuoto
linktitle: Aggiungi documento allo spazio vuoto
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere un documento a un documento di destinazione vuoto in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/append-document-to-blank/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per aggiungere il contenuto di un documento a un documento di destinazione vuoto. Il codice sorgente fornito dimostra come creare un nuovo documento, rimuoverne il contenuto e quindi aggiungervi il documento sorgente.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

-  Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory di documenti in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: crea un nuovo documento di destinazione

 Creane uno nuovo`Document` oggetto per il documento di destinazione.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Passaggio 3: rimuovi il contenuto esistente dal documento di destinazione

 Per garantire un documento di destinazione pulito, rimuovere tutto il contenuto esistente dal documento utilizzando il comando`RemoveAllChildren` metodo.

```csharp
dstDoc.RemoveAllChildren();
```

## Passaggio 4: aggiungi il documento di origine al documento di destinazione

 Aggiungi il contenuto del documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo con`ImportFormatMode.KeepSourceFormatting` opzione.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: salva il documento di destinazione

Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Ciò completa l'implementazione dell'aggiunta di un documento a un documento di destinazione vuoto utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Aggiungi documento allo spazio vuoto utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Il documento di destinazione non è vuoto, pertanto spesso viene visualizzata una pagina vuota prima del documento allegato.
	// Ciò è dovuto al fatto che il documento di base ha una sezione vuota e il nuovo documento viene avviato nella pagina successiva.
	// Rimuovere tutto il contenuto dal documento di destinazione prima di aggiungerlo.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```