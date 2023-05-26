---
title: Piè di pagina delle intestazioni dei collegamenti
linktitle: Piè di pagina delle intestazioni dei collegamenti
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come collegare intestazioni e piè di pagina durante l'unione e l'aggiunta di documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/link-headers-footers/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione Link Headers Footers di Aspose.Words per .NET. Questa funzione consente di unire e aggiungere più documenti Word collegando le intestazioni e i piè di pagina del documento di origine alla sezione precedente nel documento di destinazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Aspose.Words per .NET installato. Puoi scaricarlo dal sito Web di Aspose o installarlo tramite NuGet.
2. Visual Studio o qualsiasi altro ambiente di sviluppo C#.

## Passaggio 1: inizializzare le directory dei documenti

 Innanzitutto, devi impostare il percorso della directory dei documenti. Modificare il valore di`dataDir` variabile al percorso in cui si trovano i documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare i documenti di origine e di destinazione

 Successivamente, è necessario caricare i documenti di origine e destinazione utilizzando Aspose.Words`Document` classe. Aggiorna i nomi dei file nel file`Document` costruttore in base ai nomi dei documenti.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: impostare il documento aggiunto in modo che appaia su una nuova pagina

Per garantire che il contenuto del documento di origine venga visualizzato in una nuova pagina nel documento di destinazione, è necessario impostare il file`SectionStart` proprietà della prima sezione nel documento di origine to`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Passaggio 4: collega intestazioni e piè di pagina alla sezione precedente

 Per collegare le intestazioni e i piè di pagina del documento di origine alla sezione precedente nel documento di destinazione, puoi utilizzare il file`LinkToPrevious` metodo del`HeadersFooters` collezione. Di passaggio`true` come parametro, sovrascrivi eventuali intestazioni o piè di pagina esistenti nel documento di origine.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Passaggio 5: aggiungere il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione dell'origine venga preservata durante l'operazione di accodamento.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento finale

 Infine, salva il documento unito con le intestazioni e i piè di pagina collegati utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Esempio di codice sorgente per Link Headers Footers utilizzando Aspose.Words per .NET 

Ecco il codice sorgente completo per la funzionalità "Link Headers Footers" in C# utilizzando Aspose.Words per .NET:


```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Impostare il documento aggiunto in modo che appaia su una nuova pagina.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Collega le intestazioni e i piè di pagina nel documento di origine alla sezione precedente.
	// Ciò sovrascriverà eventuali intestazioni o piè di pagina già presenti nel documento di origine.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Questo è tutto! Hai implementato con successo la funzione Link Headers Footers utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con le intestazioni ei piè di pagina del documento di origine collegato alla sezione precedente nel documento di destinazione.