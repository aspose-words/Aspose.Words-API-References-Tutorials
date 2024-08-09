---
title: Aggiungi testo con segnalibro nel documento Word
linktitle: Aggiungi testo con segnalibro nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere testo con segnalibro in un documento Word utilizzando Aspose.Words per .NET con questa guida passo passo. Perfetto per gli sviluppatori.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/append-bookmarked-text/
---
## Introduzione

Ehilà! Hai mai provato ad aggiungere testo da una sezione con segnalibro in un documento di Word e l'hai trovato complicato? Sei fortunato! Questo tutorial ti guiderà attraverso il processo utilizzando Aspose.Words per .NET. Lo suddivideremo in semplici passaggi in modo che tu possa seguirlo facilmente. Immergiamoci e aggiungiamo il testo ai segnalibri come un professionista!

## Prerequisiti

Prima di iniziare, assicuriamoci di avere tutto ciò di cui hai bisogno:

-  Aspose.Words per .NET: assicurati di averlo installato. In caso contrario, puoi[scaricalo qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: qualsiasi ambiente di sviluppo .NET come Visual Studio.
- Conoscenza di base di C#: comprendere i concetti di base della programmazione C# sarà utile.
- Documento Word con segnalibri: un documento Word con segnalibri impostati, che utilizzeremo per aggiungere testo.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari. In questo modo avremo a portata di mano tutti gli strumenti di cui abbiamo bisogno.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Analizziamo l'esempio in passaggi dettagliati.

## Passaggio 1: caricare il documento e inizializzare le variabili

Va bene, iniziamo caricando il nostro documento Word e inizializzando le variabili di cui avremo bisogno.

```csharp
// Caricare i documenti di origine e di destinazione.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Inizializza l'importatore di documenti.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Trova il segnalibro nel documento di origine.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Passaggio 2: identificare i paragrafi di inizio e fine

Ora individuiamo i paragrafi in cui inizia e finisce il segnalibro. Questo è fondamentale poiché dobbiamo gestire il testo entro questi limiti.

```csharp
// Questo è il paragrafo che contiene l'inizio del segnalibro.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// Questo è il paragrafo che contiene la fine del segnalibro.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## Passaggio 3: convalida dei genitori del paragrafo

Dobbiamo assicurarci che i paragrafi di inizio e fine abbiano lo stesso genitore. Questo è uno scenario semplice per mantenere le cose semplici.

```csharp
// Limitiamoci a uno scenario ragionevolmente semplice.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Passaggio 4: identificare il nodo da arrestare

Successivamente, dobbiamo determinare il nodo in cui smetteremo di copiare il testo. Questo sarà il nodo immediatamente dopo la fine del paragrafo.

```csharp
// Vogliamo copiare tutti i paragrafi dal paragrafo iniziale fino al paragrafo finale (incluso),
// quindi il nodo in cui ci fermiamo è quello successivo alla fine del paragrafo.
Node endNode = endPara.NextSibling;
```

## Passaggio 5: aggiungi il testo aggiunto ai segnalibri al documento di destinazione

Infine, eseguiamo il loop dei nodi dal paragrafo iniziale al nodo dopo il paragrafo finale e aggiungiamoli al documento di destinazione.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Questo crea una copia del nodo corrente e lo importa (lo rende valido) nel contesto
    // del documento di destinazione. Importare significa regolare correttamente gli stili e gli identificatori degli elenchi.
    Node newNode = importer.ImportNode(curNode, true);

    // Aggiungi il nodo importato al documento di destinazione.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Salva il documento di destinazione con il testo aggiunto.
dstDoc.Save("appended_document.docx");
```

## Conclusione

Ed ecco qua! Hai aggiunto con successo il testo da una sezione con segnalibro in un documento di Word utilizzando Aspose.Words per .NET. Questo potente strumento semplifica la manipolazione dei documenti e ora hai un altro asso nella manica. Buona programmazione!

## Domande frequenti

### Posso aggiungere testo da più segnalibri in una volta sola?
Sì, puoi ripetere la procedura per ciascun segnalibro e aggiungere il testo di conseguenza.

### Cosa succede se i paragrafi di inizio e fine hanno genitori diversi?
L'esempio attuale presuppone che abbiano lo stesso genitore. Per genitori diversi è necessaria una gestione più complessa.

### Posso mantenere la formattazione originale del testo aggiunto?
 Assolutamente! IL`ImportFormatMode.KeepSourceFormatting` garantisce che la formattazione originale venga preservata.

### È possibile aggiungere testo in una posizione specifica nel documento di destinazione?
Sì, puoi aggiungere il testo in qualsiasi posizione navigando fino al nodo desiderato nel documento di destinazione.

### Cosa succede se devo aggiungere testo da un segnalibro a una nuova sezione?
Puoi creare una nuova sezione nel documento di destinazione e aggiungere lì il testo.