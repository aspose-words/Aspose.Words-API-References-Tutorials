---
title: Formattazione del paragrafo
linktitle: Formattazione del paragrafo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come applicare la formattazione personalizzata ai tuoi paragrafi con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/paragraph-formatting/
---

In questo tutorial, ti illustreremo come utilizzare la funzionalità di formattazione dei paragrafi con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: creazione e configurazione del documento

Per iniziare, crea un nuovo documento e un oggetto DocumentBuilder associato. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: formattazione del paragrafo

Applicheremo ora la formattazione al paragrafo utilizzando le proprietà disponibili nell'oggetto ParagraphFormat dell'oggetto DocumentBuilder. Ecco come:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat. LeftIndent = 50;
paragraphFormat. RightIndent = 50;
paragraphFormat. SpaceAfter = 25;
```

## Passaggio 3: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
```

### Esempio di codice sorgente per la formattazione dei paragrafi utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzionalità di formattazione dei paragrafi con Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.Alignment = ParagraphAlignment.Center;
	paragraphFormat.LeftIndent = 50;
	paragraphFormat.RightIndent = 50;
	paragraphFormat.SpaceAfter = 25;

	builder.Writeln(
		"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
	builder.Writeln(
		"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

	doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
	
```

Con questo codice sarai in grado di applicare una formattazione diversa ai tuoi paragrafi usando Aspose.Words per .NET.

