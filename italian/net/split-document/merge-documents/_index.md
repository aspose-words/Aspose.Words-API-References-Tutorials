---
title: Unisci documenti di Word
linktitle: Unisci documenti
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come unire più documenti di Word utilizzando Aspose.Words per .NET. Questa potente API semplifica il processo di unione dei documenti, rendendolo efficiente e diretto.
type: docs
weight: 10
url: /it/net/split-document/merge-documents/
---

In questo tutorial, ti illustreremo come unire più documenti di Word utilizzando la funzione Unisci documenti di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e ottenere un documento unito contenente tutti i documenti di origine.

## Passaggio 1: cerca i documenti da unire

Prima di unire i documenti, dobbiamo individuare i documenti di origine da unire. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cerca i documenti da unire.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Passaggio 2: unisci i documenti

Ora uniremo i documenti uno per uno per creare un documento unito finale. Ecco come:

```csharp
// Apri la prima parte del documento risultante.
Document sourceDoc = new Document(sourceDocumentPath);

// Crea un nuovo documento risultante.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Unire i documenti uno per uno.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Esempio di codice sorgente per Merge Documents utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Merge Documents di Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Trova i documenti usando per unire.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Apri la prima parte del documento risultante.
Document sourceDoc = new Document(sourceDocumentPath);

// Crea un nuovo documento risultante.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Unisci le parti del documento una per una.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## Conclusione

Congratulazioni! Hai imparato come unire più documenti di Word utilizzando la funzione Unisci documenti di Aspose.Words per .NET. Seguendo il codice sorgente fornito, puoi combinare documenti separati in un unico documento unito preservando la formattazione di ciascun documento sorgente.

L'unione di documenti può essere utile quando si desidera consolidare informazioni da più fonti o creare un documento unificato da singole parti. Aspose.Words per .NET fornisce una potente API che semplifica il processo di unione dei documenti, rendendolo efficiente e diretto.

Sentiti libero di esplorare altre funzionalità offerte da Aspose.Words per .NET per migliorare le tue capacità di elaborazione dei documenti e semplificare il tuo flusso di lavoro.

### Domande frequenti

#### Come posso unire documenti con formattazione diversa?

 Quando si uniscono i documenti, Aspose.Words per .NET offre la possibilità di preservare la formattazione di ciascun documento di origine. Utilizzando il`ImportFormatMode.KeepSourceFormatting` opzione, il documento unito manterrà la formattazione dei documenti originali. Se desideri applicare una formattazione coerente in tutto il documento unito, puoi modificare la formattazione utilizzando l'API Aspose.Words dopo aver unito i documenti.

#### Posso unire documenti in diversi formati?

Sì, Aspose.Words per .NET supporta l'unione di documenti in vari formati, tra cui DOCX, DOC, RTF e altro. Puoi caricare documenti di diversi formati nell'API Aspose.Words e unirli in un unico documento indipendentemente dai loro formati originali.

#### Posso unire documenti con strutture complesse, come tabelle e immagini?

Assolutamente! Aspose.Words per .NET è in grado di unire documenti con strutture complesse, incluse tabelle, immagini, intestazioni, piè di pagina e altro. L'API gestisce il processo di unione preservando l'integrità e il layout del contenuto in ciascun documento.

#### È possibile unire documenti con orientamenti o dimensioni della pagina diversi?

Sì, Aspose.Words per .NET gestisce documenti con diversi orientamenti o dimensioni della pagina durante il processo di unione. Il documento unito risultante si adatterà ai diversi orientamenti e dimensioni della pagina dei documenti di origine.