---
title: Aggiungi forma di gruppo
linktitle: Aggiungi forma di gruppo
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere una forma di gruppo con più forme a un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-shapes/add-group-shape/
---

Questo tutorial spiega come aggiungere una forma di gruppo contenente più forme a un documento di Word utilizzando Aspose.Words per .NET. Le forme di gruppo ti consentono di combinare e manipolare più forme come un'unica entità.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui desideri salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un nuovo documento e una forma di gruppo
 Crea una nuova istanza di`Document` classe e`GroupShape` oggetto di lavorare con il documento.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Passaggio 3: crea e aggiungi forme a GroupShape
 Crea forme individuali come`accentBorderShape`E`actionButtonShape` usando il`Shape` classe. Personalizza le loro proprietà come desiderato. Aggiungi queste forme a`groupShape` oggetto.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Passaggio 4: imposta le dimensioni per GroupShape
 Imposta la larghezza, l'altezza e le dimensioni delle coordinate per il file`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Passaggio 5: inserire GroupShape nel documento
 Creare un`DocumentBuilder` oggetto e inserire il`groupShape` nel documento utilizzando il file`InsertNode` metodo.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Passaggio 6: salva il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Codice sorgente di esempio per Aggiungi forma di gruppo utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Questo è tutto! Hai aggiunto con successo una forma di gruppo contenente più forme al tuo documento Word utilizzando Aspose.W