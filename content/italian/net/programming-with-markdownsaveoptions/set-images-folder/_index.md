---
title: Imposta la cartella delle immagini
linktitle: Imposta la cartella delle immagini
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare la cartella delle immagini durante l'esportazione in Markdown con Aspose.Words per .NET. Personalizza il posizionamento delle immagini per una migliore organizzazione e integrazione.
type: docs
weight: 10
url: /it/net/programming-with-markdownsaveoptions/set-images-folder/
---

Ecco una guida passo passo per spiegare il seguente codice sorgente C# che aiuta a impostare la cartella delle immagini per le opzioni di esportazione Markdown utilizzando la libreria Aspose.Words per .NET. Assicurati di aver incluso la libreria Aspose.Words nel tuo progetto prima di utilizzare questo codice.

## Passaggio 1: imposta il percorso della directory del documento

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Assicurati di specificare il percorso corretto della directory dei documenti in cui si trova il documento contenente le immagini.

## Passaggio 2: carica il documento contenente le immagini

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Carichiamo il documento specificato che contiene le immagini che vogliamo esportare con le opzioni Markdown.

## Passaggio 3: imposta la cartella delle immagini per le opzioni di esportazione Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Creiamo un'istanza di`MarkdownSaveOptions` e imposta il percorso della cartella delle immagini utilizzando il file`ImagesFolder` proprietà. Assicurati di specificare il percorso corretto della cartella in cui desideri salvare le immagini esportate.

## Passaggio 4: salva il documento con le opzioni di esportazione Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Salviamo il documento in un flusso di memoria utilizzando le opzioni di esportazione Markdown specificate. Puoi quindi utilizzare il flusso per eseguire altre operazioni, come il salvataggio del contenuto Markdown in un file.

### Codice sorgente di esempio per impostare la cartella delle immagini per MarkdownSaveOptions con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Questo codice sorgente mostra come caricare un documento che contiene immagini e quindi impostare la cartella delle immagini per le opzioni di esportazione Markdown. Utilizzando le opzioni specificate, il documento viene quindi salvato in un flusso di memoria. Ciò consente di personalizzare la posizione della cartella delle immagini durante l'esportazione del contenuto Markdown.