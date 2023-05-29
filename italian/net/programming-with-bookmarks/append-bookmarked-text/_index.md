---
title: Aggiungi testo con segnalibro
linktitle: Aggiungi testo con segnalibro
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come aggiungere testo da un segnalibro in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/append-bookmarked-text/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Aggiungi testo con segnalibro nella libreria Aspose.Words per .NET. Questa funzionalità consente di aggiungere il testo contenuto in un segnalibro specifico di un documento Word a un altro documento.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: ottenere paragrafi dal segnalibro

 Prima di iniziare ad aggiungere il testo del segnalibro, dobbiamo ottenere i paragrafi che contengono l'inizio e la fine del segnalibro. Questo può essere fatto accedendo al file`BookmarkStart` E`BookmarkEnd` proprietà del segnalibro:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Passaggio 2: controlla i paragrafi principali

Controlliamo se l'inizio e la fine dei paragrafi hanno genitori validi, cioè se appartengono davvero a un paragrafo. In caso contrario, generiamo un'eccezione:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Passaggio 3: controlla i genitori dei paragrafi

Controlliamo se i paragrafi iniziali e finali hanno lo stesso genitore. In caso contrario, significa che i paragrafi non sono contenuti nella stessa sezione o documento e stiamo generando un'eccezione:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Passaggio 4: copia i paragrafi

Iteriamo attraverso i nodi (paragrafi) dal paragrafo iniziale al paragrafo finale. Per ogni nodo, creiamo una copia e la importiamo nel contesto del documento di destinazione:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Codice sorgente di esempio per aggiungere testo con segnalibro utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'aggiunta di testo da un segnalibro utilizzando Aspose.Words per .NET:

```csharp

	// Questo è il paragrafo che contiene l'inizio del segnalibro.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Questo è il paragrafo che contiene la fine del segnalibro.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Limitiamoci a uno scenario ragionevolmente semplice.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Vogliamo copiare tutti i paragrafi dal paragrafo iniziale fino al paragrafo finale (incluso),
	// quindi il nodo al quale ci fermiamo è uno dopo la fine del paragrafo.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// Questo crea una copia del nodo corrente e lo importa (lo rende valido) nel contesto
		// del documento di destinazione. Importare significa regolare correttamente gli stili e gli identificatori di elenco.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per comprendere come utilizzare la funzione Aggiungi testo con segnalibro di Aspose.Words per .NET. Abbiamo seguito una guida dettagliata per ottenere paragrafi da un segnalibro, verificare i genitori e copiare paragrafi in un altro documento.