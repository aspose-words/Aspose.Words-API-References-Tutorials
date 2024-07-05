---
title: Rimuovi i piè di pagina delle intestazioni della fonte
linktitle: Rimuovi i piè di pagina delle intestazioni della fonte
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come rimuovere intestazioni e piè di pagina durante l'unione e l'aggiunta di documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/remove-source-headers-footers/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzionalità Rimuovi piè di pagina intestazioni sorgente di Aspose.Words per .NET. Questa funzionalità ti consente di unire e aggiungere documenti Word rimuovendo intestazioni e piè di pagina dal documento di origine.

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

## Passaggio 3: rimuovere intestazioni e piè di pagina dalle sezioni del documento di origine

 Per rimuovere intestazioni e piè di pagina da ciascuna sezione del documento di origine, puoi scorrere le sezioni utilizzando a`foreach` loop e chiama il`ClearHeadersFooters` metodo.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Passaggio 4: disabilita l'impostazione "LinkToPrevious" per HeadersFooters

Anche dopo aver cancellato intestazioni e piè di pagina dal documento di origine, esiste la possibilità che l'impostazione "LinkToPrevious" per`HeadersFooters` può ancora essere impostato. Per evitare questo comportamento, è necessario impostarlo esplicitamente su`false` per la prima sezione`HeadersFooters` proprietà.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Passaggio 5: aggiungi il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione di origine venga preservata durante l'operazione di aggiunta.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento finale

 Infine, salva il documento unito con la funzione Rimuovi piè di pagina intestazioni sorgente abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Codice sorgente di esempio per rimuovere piè di pagina intestazioni sorgente utilizzando Aspose.Words per .NET 

Ecco il codice sorgente completo per la funzionalità "Rimuovi piè di pagina intestazioni sorgente" in C# utilizzando Aspose.Words per .NET:


```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Rimuovi le intestazioni e i piè di pagina da ciascuna sezione del documento di origine.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Anche dopo che le intestazioni e i piè di pagina sono stati cancellati dal documento di origine, l'impostazione "LinkToPrevious".
	// per HeadersFooters è ancora possibile impostare. Ciò farà sì che le intestazioni e i piè di pagina continuino dalla destinazione
	// documento. Dovrebbe essere impostato su false per evitare questo comportamento.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Questo è tutto! Hai implementato con successo la funzionalità Rimuovi piè di pagina intestazioni sorgente utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con le intestazioni e i piè di pagina rimossi dal documento di origine.