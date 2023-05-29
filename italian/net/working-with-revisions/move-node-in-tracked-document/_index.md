---
title: Sposta nodo nel documento tracciato
linktitle: Sposta nodo nel documento tracciato
second_title: Riferimento all'API Aspose.Words per .NET
description: Sposta i nodi in un documento tracciato con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/move-node-in-tracked-document/
---

In questa guida dettagliata, ti illustreremo come spostare un nodo in un documento Word tracciato utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: creazione del documento

Il primo passo è creare un nuovo documento e aggiungere paragrafi.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Passaggio 2: tenere traccia delle revisioni

Abiliteremo il tracciamento delle revisioni nel documento.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Passaggio 3: sposta un nodo

Sposteremo un nodo (paragrafo) da una posizione all'altra durante la generazione delle revisioni.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Passaggio 4: interrompere il monitoraggio delle recensioni

Interromperemo il monitoraggio delle revisioni nel documento.

```csharp
doc.StopTrackRevisions();
```

## Passaggio 5: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Esempio di codice sorgente per Sposta nodo nel documento tracciato utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per spostare un nodo in un documento tracciato utilizzando Aspose.Words per .NET:


```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Inizia a monitorare le revisioni.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Generare revisioni quando si sposta un nodo da una posizione a un'altra.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Interrompi il processo di monitoraggio delle revisioni.
doc.StopTrackRevisions();

// Ci sono 3 paragrafi aggiuntivi nell'intervallo di spostamento.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

