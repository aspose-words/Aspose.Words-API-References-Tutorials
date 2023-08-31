---
title: Aggiorna layout di pagina
linktitle: Aggiorna layout di pagina
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiornare il layout di pagina quando unisci e aggiungi documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/update-page-layout/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione Aggiorna layout di pagina di Aspose.Words per .NET. Questa funzione assicura che il layout della pagina venga aggiornato correttamente quando si uniscono e si aggiungono documenti di Word.

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

## Passaggio 3: aggiornare il layout di pagina per il documento di destinazione

 Per assicurarti che il layout di pagina venga aggiornato correttamente prima di aggiungere il documento di origine, puoi chiamare il metodo`UpdatePageLayout` metodo sul documento di destinazione.

```csharp
dstDoc.UpdatePageLayout();
```

## Passaggio 4: aggiungere il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione dell'origine venga preservata durante l'operazione di accodamento.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: aggiorna nuovamente il layout della pagina

 Dopo aver aggiunto il documento di origine, è necessario chiamare il file`UpdatePageLayout` metodo sul documento di destinazione per garantire che eventuali modifiche apportate dopo l'operazione di accodamento si riflettano nell'output sottoposto a rendering.

```csharp
dstDoc.UpdatePageLayout();
```

## Passaggio 6: salvare il documento finale

 Infine, salva il documento unito con la funzione Aggiorna layout di pagina abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Codice sorgente di esempio per l'aggiornamento del layout di pagina utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzionalità "Aggiorna layout di pagina" in C# utilizzando Aspose.Words per .NET:

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Se il documento di destinazione è reso in PDF, immagine ecc.
	// o UpdatePageLayout viene chiamato prima del documento di origine. è aggiunto,
	// quindi eventuali modifiche apportate dopo non si rifletteranno nell'output di rendering
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Per aggiornare le modifiche all'output sottoposto a rendering, UpdatePageLayout deve essere richiamato di nuovo.
	// Se non viene richiamato di nuovo, il documento aggiunto non verrà visualizzato nell'output del rendering successivo.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Questo è tutto! Hai implementato correttamente la funzione Aggiorna layout di pagina utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con il layout di pagina aggiornato correttamente.