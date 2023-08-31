---
title: Aggiorna il disegno artistico intelligente
linktitle: Aggiorna il disegno artistico intelligente
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiornare il disegno Smart Art in un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-shapes/update-smart-art-drawing/
---

Questo tutorial spiega come aggiornare il disegno Smart Art in un documento Word utilizzando Aspose.Words per .NET. Iterando le forme nel documento e controllando se hanno Smart Art, puoi aggiornare il disegno Smart Art per riflettere eventuali modifiche apportate ai suoi dati.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e Word Processing con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento
 Carica il documento Word che contiene il disegno Smart Art utilizzando il file`Document` costruttore di classe.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Passaggio 3: aggiorna il disegno Smart Art
 Scorrere le forme nel documento utilizzando il file`GetChildNodes` metodo con il`NodeType.Shape` parametro. Controlla se ogni forma ha Smart Art usando il`HasSmartArt` proprietà e, se vero, chiama la proprietà`UpdateSmartArtDrawing` metodo per aggiornare il disegno Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Esempio di codice sorgente per l'aggiornamento di Smart Art Drawing utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Questo è tutto! Hai aggiornato correttamente il disegno Smart Art nel tuo documento Word utilizzando Aspose.Words per .NET.