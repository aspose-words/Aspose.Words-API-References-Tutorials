---
title: Rimuovi il sommario nel documento di Word
linktitle: Rimuovi il sommario nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come rimuovere il sommario in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/remove-content/remove-table-of-contents/
---
In questo tutorial, ti illustreremo come rimuovere il sommario in un documento Word utilizzando la libreria Aspose.Words per .NET. Il sommario a volte può essere ridondante o non necessario e questo codice ti aiuterà a rimuoverlo in modo efficace. Forniremo una guida dettagliata per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto
- Un documento di Word contenente un sommario che desideri eliminare

## Passaggio 1: definire la directory dei documenti
 Innanzitutto, devi impostare il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento
 Successivamente, caricheremo il documento di Word in un'istanza del file`Document` classe utilizzando il`Load` metodo.

```csharp
// Carica il documento
Document doc = new Document(dataDir + "your-document.docx");
```

## Passaggio 3: elimina il sommario
 Per rimuovere il sommario, eseguiremo un ciclo del tipo TOC (tabella dei contenuti).`FieldStart` nodi nel documento. Archivieremo questi nodi in modo da potervi accedere rapidamente e creare un elenco di nodi da eliminare.

```csharp
// Memorizza i nodi FieldStart dei campi TOC nel documento per un rapido accesso.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Questo è un elenco per memorizzare i nodi trovati all'interno del TOC specificato. Saranno cancellati alla fine di questo metodo.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Controlla se esiste l'indice TOC specificato.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // È più sicuro archiviare questi nodi ed eliminarli tutti alla fine.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Quando incontriamo un nodo FieldEnd di tipo FieldTOC,
     //sappiamo di essere alla fine dell'attuale TOC e ci fermiamo qui.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Esempio di codice sorgente per Rimuovi sommario utilizzando Aspose.Words per .NET 
```csharp

//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Carica il documento
Document doc = new Document(dataDir + "your-document.docx");

// Memorizza i nodi FieldStart dei campi TOC nel documento per un rapido accesso.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Questo è un elenco per memorizzare i nodi trovati all'interno del TOC specificato. Saranno rimossi alla fine di questo metodo.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Assicurarsi che il TOC specificato dall'indice passato esista.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// È più sicuro archiviare questi nodi ed eliminarli tutti in una volta in un secondo momento.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Quando incontriamo un nodo FieldEnd di tipo FieldTOC,
	// sappiamo di essere alla fine dell'attuale TOC e ci fermiamo qui.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Conclusione
In questo tutorial, abbiamo presentato una guida passo passo per rimuovere il sommario da un documento Word utilizzando la libreria Aspose.Words per .NET. Seguendo il codice e le istruzioni fornite, puoi facilmente eliminare il sommario e migliorare il layout del tuo documento. Ricordarsi di adattare il percorso della directory ei nomi dei file in base alle proprie esigenze specifiche.

### FAQ

#### D: Perché dovrei usare Aspose.Words per rimuovere il sommario in un documento di Word?

R: Aspose.Words è una libreria di classi potente e versatile per la manipolazione di documenti Word nelle applicazioni .NET. Usando Aspose.Words, puoi rimuovere efficacemente il sommario dai tuoi documenti, il che può essere utile se il sommario è ridondante o non necessario. Ciò consente di personalizzare il contenuto del documento e migliorarne la presentazione complessiva.

#### D: Come faccio a caricare un documento in Aspose.Words per .NET?

R: Per rimuovere il sommario in un documento Word, devi prima caricare il documento in memoria utilizzando il metodo Load() di Aspose.Words. Ecco un codice di esempio per caricare un documento da una directory specifica:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento
Document doc = new Document(dataDir + "your-document.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo del documento.

#### D: Come rimuovo il sommario in un documento usando Aspose.Words?

 A: Per rimuovere il sommario, è necessario scorrere il file`FieldStart` digitare i nodi del TOC nel documento. È possibile archiviare questi nodi per un accesso rapido e creare un elenco di nodi da eliminare. Ecco un codice di esempio:

```csharp
// Memorizza i nodi FieldStart dei campi TOC nel documento per un rapido accesso.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Questo è un elenco per memorizzare i nodi trovati all'interno del TOC specificato. Saranno cancellati alla fine di questo metodo.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Controlla se l'indice del sommario specificato esiste.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// È più sicuro archiviare questi nodi ed eliminarli tutti alla fine.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Quando incontriamo un nodo FieldEnd di tipo FieldTOC,
//sappiamo di essere alla fine dell'attuale TOC e ci fermiamo qui.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### D: Come salvare il documento modificato in Aspose.Words per .NET?

R: Dopo aver eliminato l'indice, è necessario salvare il documento modificato utilizzando il metodo Save(). Specificare il percorso e il formato del file di output desiderato (ad esempio, DOCX) per il documento modificato. Ecco un codice di esempio:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```