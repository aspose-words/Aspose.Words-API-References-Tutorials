---
title: Mantieni la fonte insieme
linktitle: Mantieni la fonte insieme
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare Aspose.Words per .NET per unire e aggiungere documenti Word mantenendo il contenuto di origine insieme al documento di destinazione.
type: docs
weight: 10
url: /it/net/join-and-append-documents/keep-source-together/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzionalità Keep Source Together di Aspose.Words per .NET. Questa funzionalità ti consente di unire e aggiungere più documenti Word mantenendo il contenuto del documento di origine insieme al contenuto del documento di destinazione. 

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Passaggio 3: impostare il documento di origine in modo che venga visualizzato dopo il contenuto del documento di destinazione

 Per garantire che il documento di origine venga visualizzato immediatamente dopo il contenuto del documento di destinazione, è necessario impostare il file`SectionStart` proprietà della prima sezione nel documento di origine a`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Passaggio 4: impostare la formattazione del paragrafo "Conserva con successivo" per il documento di origine

 Per mantenere insieme i paragrafi nel documento di origine, è possibile scorrere ciascun paragrafo nel documento e impostare il file`KeepWithNext` proprietà a`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Passaggio 5: aggiungi il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione di origine venga preservata durante l'operazione di aggiunta.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento finale

Infine, salva il documento unito con la funzione "Keep Source Together" abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Codice sorgente di esempio per Keep Source Together utilizzando Aspose.Words per .NET 

Ecco il codice sorgente completo per la funzionalità "Keep Source Together" in C# utilizzando Aspose.Words per .NET:


```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Imposta il documento di origine in modo che venga visualizzato subito dopo il contenuto del documento di destinazione.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Questo è tutto! Hai implementato con successo la funzionalità Keep Source Together utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con i paragrafi del documento di origine mantenuti insieme.