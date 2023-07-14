---
title: Scollega intestazioni piè di pagina
linktitle: Scollega intestazioni piè di pagina
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come unire e aggiungere documenti Word mentre scolleghi intestazioni e piè di pagina utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/unlink-headers-footers/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione Unlink Headers Footers di Aspose.Words per .NET. Questa funzione consente di unire e aggiungere documenti di Word scollegando intestazioni e piè di pagina dal documento di origine.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Aspose.Words per .NET installato. Puoi scaricarlo dal sito Web di Aspose o installarlo tramite NuGet.
2. Visual Studio o qualsiasi altro ambiente di sviluppo C#.

## Passaggio 1: inizializzare le directory dei documenti

 Innanzitutto, devi impostare il percorso della directory dei documenti. Modificare il valore di`dataDir`variabile al percorso in cui si trovano i documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare i documenti di origine e di destinazione

 Successivamente, è necessario caricare i documenti di origine e destinazione utilizzando Aspose.Words`Document` classe. Aggiorna i nomi dei file nel file`Document` costruttore in base ai nomi dei documenti.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: scollegare intestazioni e piè di pagina nel documento di origine

 Per scollegare le intestazioni e i piè di pagina nel documento di origine dalla continuazione delle intestazioni e dei piè di pagina del documento di destinazione, è necessario impostare il`LinkToPrevious`proprietà del`HeadersFooters` raccolta nella prima sezione del documento di origine a`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Passaggio 4: aggiungere il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione dell'origine venga preservata durante l'operazione di accodamento.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: salvare il documento finale

Infine, salva il documento unito con la funzione Scollega intestazioni piè di pagina abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Esempio di codice sorgente per Unlink Headers Footers utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzionalità "Unlink Headers Footers" in C# utilizzando Aspose.Words per .NET:

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Scollega le intestazioni e i piè di pagina nel documento di origine per interrompere questa operazione
	// dal continuare le intestazioni e i piè di pagina del documento di destinazione.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Questo è tutto! Hai implementato con successo la funzione Unlink Headers Footers utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con le intestazioni e i piè di pagina del documento di origine scollegato dal documento di destinazione.