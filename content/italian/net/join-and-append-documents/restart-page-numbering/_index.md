---
title: Riavvia la numerazione delle pagine
linktitle: Riavvia la numerazione delle pagine
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come riavviare la numerazione delle pagine durante l'unione e l'aggiunta di documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/restart-page-numbering/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione Riavvia numerazione delle pagine di Aspose.Words per .NET. Questa funzionalità consente di unire e aggiungere documenti Word riavviando la numerazione delle pagine nel documento di origine.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Aspose.Words per .NET installato. È possibile scaricarlo dal sito Web Aspose o installarlo tramite NuGet.
2. Visual Studio o qualsiasi altro ambiente di sviluppo C#.

## Passaggio 1: inizializzare le directory dei documenti

 Innanzitutto, devi impostare il percorso della directory dei documenti. Modificare il valore di`dataDir` variabile al percorso in cui si trovano i tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare i documenti di origine e di destinazione

 Successivamente, è necessario caricare i documenti di origine e di destinazione utilizzando Aspose.Words`Document` classe. Aggiorna i nomi dei file nel file`Document` costruttore in base ai nomi dei documenti.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: impostare il documento di origine su Riavvia numerazione delle pagine

 Per riavviare la numerazione delle pagine nel documento di origine, è necessario impostare il file`SectionStart` proprietà della prima sezione nel documento di origine a`SectionStart.NewPage` e impostare il`RestartPageNumbering` proprietà a`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Passaggio 4: aggiungi il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione di origine venga preservata durante l'operazione di aggiunta.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: salva il documento finale

 Infine, salva il documento unito con la funzione Riavvia numerazione pagine abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Codice sorgente di esempio per riavviare la numerazione delle pagine utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzionalità "Riavvia numerazione delle pagine" in C# utilizzando Aspose.Words per .NET:
 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Questo è tutto! Hai implementato con successo la funzionalità Riavvia numerazione delle pagine utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con la numerazione delle pagine riavviata nel documento di origine.