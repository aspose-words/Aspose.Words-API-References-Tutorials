---
title: Mantieni insieme la fonte
linktitle: Mantieni insieme la fonte
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare Aspose.Words per .NET per unire e aggiungere documenti Word mantenendo il contenuto di origine insieme al documento di destinazione.
type: docs
weight: 10
url: /it/net/join-and-append-documents/keep-source-together/
---

Questo tutorial ti guiderà attraverso il processo di utilizzo della funzione Keep Source Together di Aspose.Words per .NET. Questa funzione consente di unire e aggiungere più documenti Word mantenendo il contenuto del documento di origine insieme al contenuto del documento di destinazione. 

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Passaggio 3: impostare il documento di origine in modo che appaia dopo il contenuto del documento di destinazione

 Per garantire che il documento di origine appaia subito dopo il contenuto del documento di destinazione, è necessario impostare il file`SectionStart` proprietà della prima sezione nel documento di origine to`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Passaggio 4: impostare la formattazione del paragrafo "Mantieni con successivo" per il documento di origine

 Per mantenere uniti i paragrafi nel documento di origine, puoi iterare attraverso ogni paragrafo nel documento e impostare il`KeepWithNext` proprietà a`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Passaggio 5: aggiungere il documento di origine al documento di destinazione

 Ora puoi aggiungere il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. IL`ImportFormatMode.KeepSourceFormatting` Il parametro garantisce che la formattazione dell'origine venga preservata durante l'operazione di accodamento.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento finale

 Infine, salva il documento unito con la funzione "Keep Source Together" abilitata utilizzando il file`Save` metodo del`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Esempio di codice sorgente per Keep Source Together utilizzando Aspose.Words per .NET 

Ecco il codice sorgente completo per la funzione "Keep Source Together" in C# utilizzando Aspose.Words per .NET:


```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Imposta il documento di origine in modo che appaia subito dopo il contenuto del documento di destinazione.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Questo è tutto! Hai implementato correttamente la funzione Keep Source Together utilizzando Aspose.Words per .NET. Il documento finale conterrà il contenuto unito con i paragrafi nel documento di origine tenuti insieme.