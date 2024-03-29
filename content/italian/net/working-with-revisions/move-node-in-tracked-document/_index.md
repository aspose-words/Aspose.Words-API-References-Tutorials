---
title: Sposta nodo nel documento tracciato
linktitle: Sposta nodo nel documento tracciato
second_title: API di elaborazione dei documenti Aspose.Words
description: Sposta i nodi in un documento monitorato con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/move-node-in-tracked-document/
---

In questa guida passo passo ti spiegheremo come spostare un nodo in un documento Word monitorato utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output di markdown.

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

## Passaggio 3: spostare un nodo

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

## Passaggio 4: interrompi il monitoraggio delle recensioni

Smetteremo di tenere traccia delle revisioni nel documento.

```csharp
doc.StopTrackRevisions();
```

## Passaggio 5: salvataggio del documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Codice sorgente di esempio per Move Node In Tracked Document utilizzando Aspose.Words per .NET

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

// Genera revisioni quando si sposta un nodo da una posizione a un'altra.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Interrompere il processo di monitoraggio delle revisioni.
doc.StopTrackRevisions();

// Ci sono 3 paragrafi aggiuntivi nell'intervallo di spostamento.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Conclusione

In questo tutorial, abbiamo imparato come spostare un nodo in un documento Word monitorato utilizzando Aspose.Words per .NET. Seguendo i passaggi di creazione del documento, abilitazione del tracciamento delle revisioni, spostamento del nodo e interruzione del tracciamento delle revisioni, siamo stati in grado di eseguire questa manipolazione con successo. Aspose.Words per .NET è un potente strumento per l'elaborazione di parole con documenti Word e offre funzionalità avanzate per la gestione delle revisioni. Ora puoi utilizzare questa conoscenza per spostare i nodi nei tuoi documenti Word mentre tieni traccia delle revisioni utilizzando Aspose.Words per .NET.

### Domande frequenti

#### D: Come posso abilitare il monitoraggio delle revisioni in un documento Aspose.Words per .NET?

R: Per abilitare il monitoraggio delle revisioni in un documento Aspose.Words per .NET, è possibile utilizzare il file`StartTrackRevisions` metodo del`Document` oggetto. Questo metodo prende come parametri il nome dell'autore delle revisioni e la data di inizio del follow-up delle revisioni.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### D: Come posso spostare un nodo in un documento tracciato senza generare revisioni?

 R: Se desideri spostare un nodo in un documento monitorato senza generare revisioni, puoi utilizzare il file`Remove` E`InsertAfter` O`InsertBefore` metodi del`Node` oggetto. Ad esempio, per spostare un paragrafo dopo un altro paragrafo, puoi utilizzare il seguente codice:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### D: Come posso interrompere il monitoraggio delle revisioni in un documento Aspose.Words per .NET?

 R: Per interrompere il monitoraggio delle revisioni in un documento Aspose.Words per .NET, è possibile utilizzare il file`StopTrackRevisions` metodo del`Document` oggetto.

```csharp
doc.StopTrackRevisions();
```