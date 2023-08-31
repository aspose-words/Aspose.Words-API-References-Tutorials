---
title: Applicare bordi e ombreggiature al paragrafo nel documento Word
linktitle: Applicare bordi e ombreggiature al paragrafo nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come applicare bordi e ombreggiature a un paragrafo in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
In questo tutorial, ti mostreremo come applicare bordi e ombreggiature a un paragrafo in un documento Word utilizzando la funzionalità di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche alla formattazione.

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

Ora configureremo il riempimento del paragrafo specificando la trama e i colori di riempimento. Ecco come:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Passaggio 4: aggiungi contenuto

Aggiungeremo alcuni contenuti formattati al paragrafo. Ecco come:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Passaggio 3: salvataggio del documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Codice sorgente di esempio per Applicare bordi e ombreggiatura al paragrafo utilizzando Aspose.Words per .NET

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

## Conclusione

In questo tutorial, abbiamo imparato come applicare bordi e ombreggiature a un paragrafo in un documento Word utilizzando Aspose.Words per .NET. Configurando i paragrafi`Borders` E`Shading` proprietà, siamo stati in grado di impostare lo stile del bordo, il colore della linea e il colore di riempimento per il paragrafo. Aspose.Words per .NET fornisce potenti funzionalità di formattazione per personalizzare l'aspetto dei paragrafi e migliorare la rappresentazione visiva dei tuoi documenti.

### Domande frequenti

#### D: Come posso applicare bordi e ombreggiature a un paragrafo in un documento Word utilizzando Aspose.Words per .NET?

R: Per applicare bordi e ombreggiature a un paragrafo in un documento di Word utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:
1.  Creare un nuovo documento e a`DocumentBuilder` oggetto.
2.  Configura i bordi del paragrafo accedendo a`Borders` proprietà del`ParagraphFormat` e impostare lo stile del bordo per ciascun lato.
3.  Configura il riempimento del paragrafo accedendo al file`Shading` proprietà del`ParagraphFormat` e specificando la trama e i colori di riempimento.
4.  Aggiungi contenuto al paragrafo utilizzando il`Write` metodo del`DocumentBuilder`.
5.  Salvare il documento utilizzando il file`Save` metodo.

#### D: Come posso impostare lo stile del bordo per ciascun lato del paragrafo?

 R: Per impostare lo stile del bordo per ciascun lato del paragrafo, puoi accedere a`Borders` proprietà del`ParagraphFormat` e impostare il`LineStyle` proprietà per ciascuno`BorderType` (per esempio,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). È possibile specificare diversi stili di linea come`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, eccetera.

#### D: Come posso specificare la trama e i colori di riempimento per l'ombreggiatura del paragrafo?

 R: Per specificare la trama e i colori di riempimento per l'ombreggiatura del paragrafo, puoi accedere a`Shading` proprietà del`ParagraphFormat` e impostare il`Texture` proprietà all'indice di texture desiderato (ad esempio,`TextureIndex.TextureDiagonalCross` ). Puoi anche impostare il`BackgroundPatternColor` E`ForegroundPatternColor` proprietà ai colori desiderati utilizzando il file`System.Drawing.Color` classe.