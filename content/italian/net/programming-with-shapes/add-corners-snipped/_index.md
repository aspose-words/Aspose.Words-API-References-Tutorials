---
title: Aggiungi angoli tagliati
linktitle: Aggiungi angoli tagliati
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere una forma con gli angoli ritagliati a un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-shapes/add-corners-snipped/
---

 Questo tutorial spiega come aggiungere una forma con gli angoli ritagliati a un documento Word utilizzando Aspose.Words per .NET. La forma degli angoli tagliati può essere personalizzata e inserita utilizzando il file`InsertShape` metodo.

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
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` oggetto di lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire la forma ritagliata degli angoli
 Usa il`InsertShape` metodo del`DocumentBuilder` oggetto per inserire una forma con gli angoli tagliati. Specificare il tipo di forma (in questo caso,`ShapeType.TopCornersSnipped`) e fornire la dimensione desiderata per la forma.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Passaggio 4: salva il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Codice sorgente di esempio per Aggiungi angoli ritagliati utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Questo è tutto! Hai aggiunto con successo una forma con angoli ritagliati al tuo documento Word utilizzando Aspose.Words per .NET.