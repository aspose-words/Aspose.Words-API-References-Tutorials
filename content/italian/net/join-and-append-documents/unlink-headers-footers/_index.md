---
title: Scollega intestazioni piè di pagina
linktitle: Scollega intestazioni piè di pagina
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come unire e aggiungere documenti Word scollegando intestazioni e piè di pagina utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/unlink-headers-footers/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzionalità Scollega intestazioni piè di pagina di Aspose.Words per .NET. Questa funzionalità ti consente di unire e aggiungere documenti Word scollegando intestazioni e piè di pagina dal documento di origine.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Aspose.Words per .NET installato. È possibile scaricarlo dal sito Web Aspose o installarlo tramite NuGet.
2. Visual Studio o qualsiasi altro ambiente di sviluppo C#.

## Passaggio 1: inizializzare le directory dei documenti

 Innanzitutto, devi impostare il percorso della directory dei documenti. Modificare il valore di`dataDir`variabile al percorso in cui si trovano i tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare i documenti di origine e di destinazione

 Successivamente, è necessario caricare i documenti di origine e di destinazione utilizzando Aspose.Words`Document` classe. Aggiorna i nomi dei file nel file`Document` costruttore in base ai nomi dei documenti.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: scollega intestazioni e piè di pagina nel documento di origine

 Per scollegare le intestazioni e i piè di pagina del documento di origine dalla continuazione delle intestazioni e dei piè di pagina del documento di destinazione, è necessario impostare l'opzione`LinkToPrevious` proprietà del`HeadersFooters` raccolta nella prima sezione del documento di origine a`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Passaggio 4: aggiungi il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione di origine venga preservata durante l'operazione di aggiunta.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: salva il documento finale

Infine, salva il documento unito con la funzione Scollega intestazioni piè di pagina abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Codice sorgente di esempio per Scollegare intestazioni piè di pagina utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzionalità "Unlink Headers Footers" in C# utilizzando Aspose.Words per .NET:

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Scollega le intestazioni e i piè di pagina nel documento di origine per interrompere questo problema
	// dal continuare le intestazioni e i piè di pagina del documento di destinazione.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Questo è tutto! Hai implementato con successo la funzionalità Scollega intestazioni piè di pagina utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con le intestazioni e i piè di pagina del documento di origine scollegati dal documento di destinazione.