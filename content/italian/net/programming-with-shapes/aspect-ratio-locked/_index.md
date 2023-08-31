---
title: Proporzioni bloccate
linktitle: Proporzioni bloccate
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come bloccare o sbloccare le proporzioni di una forma in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-shapes/aspect-ratio-locked/
---

Questo tutorial spiega come bloccare o sbloccare le proporzioni di una forma in un documento di Word usando Aspose.Words per .NET. Bloccando le proporzioni, puoi mantenere le proporzioni originali della forma durante il ridimensionamento.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e Word Processing con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si desidera salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un nuovo documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` opporsi a lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire una forma immagine
 Usa il`InsertImage` metodo del`DocumentBuilder` oggetto per inserire una forma immagine nel documento. Fornire il percorso del file immagine come parametro.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Passaggio 4: bloccare o sbloccare le proporzioni
 Impostare il`AspectRatioLocked` proprietà della forma a`true` O`false` rispettivamente per bloccare o sbloccare le proporzioni.

```csharp
shape.AspectRatioLocked = false; //Sblocca le proporzioni
```

## Passaggio 5: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Esempio di codice sorgente per Aspect Ratio Locked utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Questo è tutto! Hai bloccato o sbloccato correttamente le proporzioni di una forma nel documento di Word utilizzando Aspose.Words per .NET.