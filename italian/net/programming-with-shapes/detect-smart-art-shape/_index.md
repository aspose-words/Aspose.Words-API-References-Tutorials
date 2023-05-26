---
title: Rileva la forma artistica intelligente
linktitle: Rileva la forma artistica intelligente
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come rilevare le forme Smart Art in un documento Word utilizzando Aspose.Words per .NET, identificando le rappresentazioni grafiche.
type: docs
weight: 10
url: /it/net/programming-with-shapes/detect-smart-art-shape/
---

Questo tutorial spiega come rilevare le forme Smart Art in un documento Word utilizzando Aspose.Words per .NET. Le forme Smart Art sono rappresentazioni grafiche utilizzate per presentare visivamente informazioni e idee.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento
 Carica il documento Word usando il file`Document` costruttore, passando il percorso al documento come parametro.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Passaggio 3: rileva le forme artistiche intelligenti
Scorrere i nodi figlio di type`Shape` nel documento utilizzando il`GetChildNodes` metodo. Controlla se ogni forma ha Smart Art usando il`HasSmart Art` proprietà.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Passaggio 4: emettere il risultato
Stampa il conteggio delle forme con Smart Art rilevate nel documento.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Esempio di codice sorgente per Rileva Smart Art Shape utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Questo è tutto! Hai rilevato correttamente le forme Smart Art nel tuo documento Word utilizzando Aspose.Words per .NET.