---
title: Applica bordi e ombreggiatura al paragrafo
linktitle: Applica bordi e ombreggiatura al paragrafo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come applicare bordi e ombreggiatura a un paragrafo con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

In questo tutorial, ti mostreremo come applicare bordi e ombreggiature a un paragrafo utilizzando la funzionalità di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche alla formattazione.

## Passaggio 1: creazione e configurazione del documento

Per iniziare, crea un nuovo documento e un oggetto DocumentBuilder associato. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: configurazione del bordo

Ora configuriamo i bordi del paragrafo specificando lo stile del bordo per ciascun lato. Ecco come:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Passaggio 3: configurazione del riempimento

Ora configureremo il riempimento del paragrafo specificando la trama ei colori di riempimento. Ecco come:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Passaggio 4: aggiungi contenuto

Aggiungeremo del contenuto formattato al paragrafo. Ecco come:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Passaggio 3: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Esempio di codice sorgente per Applica bordi e ombreggiatura al paragrafo utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Applica bordi e ombreggiatura al paragrafo con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```
