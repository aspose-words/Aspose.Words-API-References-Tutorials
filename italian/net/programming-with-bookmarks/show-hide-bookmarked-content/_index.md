---
title: Mostra Nascondi contenuto aggiunto ai segnalibri
linktitle: Mostra Nascondi contenuto aggiunto ai segnalibri
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come mostrare o nascondere il contenuto dei segnalibri utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Mostra Nascondi contenuto con segnalibro nella libreria Aspose.Words per .NET. Questa funzione consente di mostrare o nascondere il contenuto di un segnalibro in base a una condizione specifica durante l'unione dei dati.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: ottenere il segnalibro

 Noi usiamo il`Bookmarks` proprietà dell'intervallo di documenti per ottenere il segnalibro specifico su cui vogliamo mostrare o nascondere il contenuto:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Passaggio 2: Inserimento dei campi di unione

 Usiamo un generatore di documenti`DocumentBuilder` per inserire i campi di unione necessari. Questi campi di unione imposteranno una condizione per mostrare o nascondere il contenuto del segnalibro a seconda del valore di`showHide` variabile:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Passaggio 3: spostamento del contenuto dei segnalibri

Esaminiamo il contenuto del segnalibro e lo spostiamo in modo che appaia

isse prima del segnalibro. Questo controllerà la visualizzazione o l'occultamento del contenuto in base alla condizione specificata:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Passaggio 4: spostare il resto del contenuto del segnalibro

Spostiamo il resto del contenuto del segnalibro dopo il segnalibro, utilizzando il nodo finale del segnalibro come punto di inserimento:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Passaggio 5: eseguire l'unione

 Noi usiamo il`Execute` metodo del documento`s `Stampa unione` object to execute the merge using the bookmark name and the value of the `mostraNascondi` variabile:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Codice sorgente di esempio per Mostra Nascondi contenuto con segnalibro utilizzando Aspose.Words per .NET

Ecco l'esempio completo del codice sorgente per mostrare o nascondere il contenuto dei segnalibri utilizzando Aspose.Words per .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD segnalibro}" = "vero" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzionalità Mostra Nascondi contenuto con segnalibro di Aspose.Words per .NET. Abbiamo seguito una guida dettagliata per mostrare o nascondere il contenuto di un segnalibro in base a una condizione specifica durante l'unione dei dati.