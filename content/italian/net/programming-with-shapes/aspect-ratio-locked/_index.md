---
title: Proporzioni bloccate
linktitle: Proporzioni bloccate
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come bloccare o sbloccare le proporzioni di una forma in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-shapes/aspect-ratio-locked/
---

Questo tutorial spiega come bloccare o sbloccare le proporzioni di una forma in un documento di Word utilizzando Aspose.Words per .NET. Bloccando le proporzioni, puoi mantenere le proporzioni originali della forma durante il ridimensionamento.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui desideri salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un nuovo documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder`oggetto di lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserisci una forma immagine
 Usa il`InsertImage` metodo del`DocumentBuilder` oggetto per inserire una forma di immagine nel documento. Fornire il percorso del file immagine come parametro.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Passaggio 4: blocca o sblocca le proporzioni
 Impostare il`AspectRatioLocked` proprietà della forma a`true` O`false` per bloccare o sbloccare rispettivamente le proporzioni.

```csharp
shape.AspectRatioLocked = false; //Sblocca le proporzioni
```

## Passaggio 5: salva il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Codice sorgente di esempio per proporzioni bloccate utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Questo è tutto! Hai bloccato o sbloccato con successo le proporzioni di una forma nel tuo documento Word utilizzando Aspose.Words per .NET.