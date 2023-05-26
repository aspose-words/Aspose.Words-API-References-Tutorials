---
title: Rimuovi i piè di pagina delle intestazioni di origine
linktitle: Rimuovi i piè di pagina delle intestazioni di origine
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come rimuovere intestazioni e piè di pagina durante l'unione e l'aggiunta di documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/remove-source-headers-footers/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione Remove Source Headers Footers di Aspose.Words per .NET. Questa funzione consente di unire e aggiungere documenti di Word rimuovendo intestazioni e piè di pagina dal documento di origine.

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

## Passaggio 3: rimuovere intestazioni e piè di pagina dalle sezioni del documento di origine

 Per rimuovere le intestazioni e i piè di pagina da ciascuna sezione del documento di origine, puoi scorrere le sezioni utilizzando a`foreach` loop e chiama il`ClearHeadersFooters` metodo.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Passaggio 4: disabilitare l'impostazione "LinkToPrevious" per HeadersFooters

Anche dopo aver cancellato le intestazioni e i piè di pagina dal documento di origine, è possibile che l'impostazione "LinkToPrevious" per`HeadersFooters` può ancora essere impostato. Per evitare questo comportamento, è necessario impostarlo esplicitamente su`false` per la prima sezione`HeadersFooters` proprietà.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Passaggio 5: aggiungere il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione dell'origine venga preservata durante l'operazione di accodamento.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento finale

 Infine, salva il documento unito con la funzione Rimuovi intestazioni piè di pagina abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Codice sorgente di esempio per rimuovere i piè di pagina delle intestazioni di origine utilizzando Aspose.Words per .NET 

Ecco il codice sorgente completo per la funzione "Rimuovi i piè di pagina delle intestazioni di origine" in C# utilizzando Aspose.Words per .NET:


```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Rimuovi le intestazioni e i piè di pagina da ciascuna delle sezioni nel documento di origine.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Anche dopo che le intestazioni e i piè di pagina sono stati cancellati dal documento di origine, l'impostazione "LinkToPrevious".
	// per HeadersFooters può ancora essere impostato. Ciò farà sì che le intestazioni ei piè di pagina continuino dalla destinazione
	// documento. Questo dovrebbe essere impostato su false per evitare questo comportamento.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Questo è tutto! Hai implementato correttamente la funzione Rimuovi piè di pagina intestazioni sorgente utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con le intestazioni e i piè di pagina rimossi dal documento di origine.