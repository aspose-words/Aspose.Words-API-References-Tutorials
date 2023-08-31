---
title: Aggiorna il layout della pagina
linktitle: Aggiorna il layout della pagina
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiornare il layout della pagina quando unisci e aggiungi documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/update-page-layout/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzionalità Aggiorna layout di pagina di Aspose.Words per .NET. Questa funzionalità garantisce che il layout della pagina venga aggiornato correttamente durante l'unione e l'aggiunta di documenti Word.

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

## Passaggio 3: aggiorna il layout della pagina per il documento di destinazione

 Per garantire che il layout della pagina venga aggiornato correttamente prima di aggiungere il documento di origine, puoi chiamare il file`UpdatePageLayout` metodo sul documento di destinazione.

```csharp
dstDoc.UpdatePageLayout();
```

## Passaggio 4: aggiungi il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione di origine venga preservata durante l'operazione di aggiunta.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: aggiorna nuovamente il layout della pagina

 Dopo aver aggiunto il documento di origine, è necessario chiamare il file`UpdatePageLayout` metodo sul documento di destinazione per garantire che tutte le modifiche apportate dopo l'operazione di aggiunta si riflettano nell'output sottoposto a rendering.

```csharp
dstDoc.UpdatePageLayout();
```

## Passaggio 6: salvare il documento finale

 Infine, salva il documento unito con la funzione Aggiorna layout di pagina abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Codice sorgente di esempio per Aggiorna layout di pagina utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzionalità "Aggiorna layout di pagina" in C# utilizzando Aspose.Words per .NET:

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Se il documento di destinazione viene sottoposto a rendering in PDF, immagine ecc.
	// oppure UpdatePageLayout viene chiamato prima del documento di origine. Viene aggiunto,
	// quindi qualsiasi modifica apportata successivamente non si rifletterà nell'output renderizzato
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Affinché le modifiche vengano aggiornate nell'output sottoposto a rendering, è necessario richiamare nuovamente UpdatePageLayout.
	// Se non viene richiamato nuovamente, il documento aggiunto non apparirà nell'output del rendering successivo.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Questo è tutto! Hai implementato con successo la funzionalità Aggiorna layout di pagina utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con il layout di pagina aggiornato correttamente.