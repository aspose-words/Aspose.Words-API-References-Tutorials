---
title: Documento di aggiunta semplice
linktitle: Documento di aggiunta semplice
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come unire e aggiungere documenti Word con formattazione conservata utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/simple-append-document/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione Simple Append Document di Aspose.Words per .NET. Questa funzione ti consente di unire e aggiungere documenti Word senza opzioni aggiuntive.

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

## Passaggio 3: aggiungere il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione dell'origine venga preservata durante l'operazione di accodamento.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 4: salvare il documento finale

 Infine, salva il documento unito con la funzione Accoda documento semplice utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Esempio di codice sorgente per Simple Append Document utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzionalità "Simple Append Document" in C# utilizzando Aspose.Words per .NET:

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Aggiungi il documento di origine al documento di destinazione senza opzioni aggiuntive.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Questo è tutto! Hai implementato con successo la funzione Simple Append Document utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con la formattazione originale preservata.