---
title: Copia il testo con segnalibro nel documento Word
linktitle: Copia il testo con segnalibro nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Copia facilmente il testo con segnalibro tra documenti Word utilizzando Aspose.Words per .NET. Scopri come con questa guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/copy-bookmarked-text/
---
## Introduzione

Ti sei mai trovato a dover copiare sezioni specifiche da un documento Word a un altro? Bene, sei fortunato! In questo tutorial ti spiegheremo come copiare il testo con segnalibri da un documento Word a un altro utilizzando Aspose.Words per .NET. Che tu stia creando un report dinamico o automatizzando la generazione di documenti, questa guida semplificherà il processo per te.

## Prerequisiti

Prima di immergerci, assicurati di avere quanto segue:

-  Aspose.Words per .NET Library: puoi scaricarlo da[Qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: Visual Studio o qualsiasi altro ambiente di sviluppo .NET.
- Conoscenza di base di C#: familiarità con la programmazione C# e il framework .NET.

## Importa spazi dei nomi

Per iniziare, assicurati di aver importato gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## Passaggio 1: caricare il documento di origine

Per prima cosa, devi caricare il documento di origine che contiene il testo con segnalibro che desideri copiare.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Qui,`dataDir` è il percorso della directory dei documenti e`Bookmarks.docx` è il documento di origine.

## Passaggio 2: identificare il segnalibro

Successivamente, identifica il segnalibro che desideri copiare dal documento di origine.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Sostituire`"MyBookmark1"` con il nome effettivo del tuo segnalibro.

## Passaggio 3: creare il documento di destinazione

Ora crea un nuovo documento in cui verrà copiato il testo con segnalibro.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Passaggio 4: importa il contenuto dei segnalibri

 Per garantire che gli stili e la formattazione vengano preservati, utilizzare`NodeImporter` per importare il contenuto con segnalibro dal documento di origine al documento di destinazione.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Passaggio 5: definire il metodo AppendBookmarkedText

Ecco dove avviene la magia. Definire un metodo per gestire la copia del testo con segnalibro:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Passaggio 6: salvare il documento di destinazione

Infine, salva il documento di destinazione per verificare il contenuto copiato.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Conclusione

E questo è tutto! Hai copiato con successo il testo con segnalibro da un documento Word a un altro utilizzando Aspose.Words per .NET. Questo metodo è potente per automatizzare le attività di manipolazione dei documenti, rendendo il flusso di lavoro più efficiente e snello.

## Domande frequenti

### Posso copiare più segnalibri contemporaneamente?
Sì, puoi scorrere più segnalibri e utilizzare lo stesso metodo per copiarli ciascuno.

### Cosa succede se il segnalibro non viene trovato?
 IL`Range.Bookmarks` la proprietà ritornerà`null`, quindi assicurati di gestire questo caso per evitare eccezioni.

### Posso preservare la formattazione del segnalibro originale?
 Assolutamente! Utilizzando`ImportFormatMode.KeepSourceFormatting` garantisce che la formattazione originale venga preservata.

### Esiste un limite alla dimensione del testo aggiunto ai segnalibri?
Non esiste un limite specifico, ma le prestazioni possono variare con documenti estremamente grandi.

### Posso copiare testo tra diversi formati di documenti Word?
Sì, Aspose.Words supporta vari formati Word e il metodo funziona su questi formati.