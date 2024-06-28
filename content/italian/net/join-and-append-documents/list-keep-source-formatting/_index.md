---
title: Elenco Mantieni formattazione sorgente
linktitle: Elenco Mantieni formattazione sorgente
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come preservare la formattazione dell'elenco durante l'unione e l'aggiunta di documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/list-keep-source-formatting/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione List Keep Source Formatting di Aspose.Words per .NET. Questa funzionalità ti consente di unire e aggiungere documenti Word preservando la formattazione originale degli elenchi.

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

Successivamente, è necessario caricare i documenti di origine e di destinazione utilizzando Aspose.Words.`Document` classe. Aggiorna i nomi dei file nel file`Document` costruttore in base ai nomi dei documenti.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Passaggio 3: impostare il documento di origine su flusso continuo

 Per garantire che il contenuto del documento di origine fluisca continuamente quando viene aggiunto al documento di destinazione, è necessario impostare il file`SectionStart` proprietà della prima sezione nel documento di origine a`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Passaggio 4: aggiungi il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting`Il parametro garantisce che la formattazione di origine, inclusa la formattazione degli elenchi, venga preservata durante l'operazione di aggiunta.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: salva il documento finale

 Infine, salva il documento unito con la funzione Elenco mantieni formattazione originale abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Codice sorgente di esempio per List Keep Source Formatting utilizzando Aspose.Words per .NET 

Ecco il codice sorgente completo per la funzionalità List Keep Source Formatting in C# utilizzando Aspose.Words per .NET:

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Aggiungi il contenuto del documento in modo che scorra continuamente.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Questo è tutto! Hai implementato con successo la funzionalità List Keep Source Formatting utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito mantenendo la formattazione dell'elenco del documento di origine.