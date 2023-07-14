---
title: Spazio tra testo asiatico e latino
linktitle: Spazio tra testo asiatico e latino
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come regolare automaticamente lo spazio tra testo asiatico e latino nel tuo documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/space-between-asian-and-latin-text/
---

In questo tutorial, ti mostreremo come utilizzare la funzione Spazio tra testo asiatico e latino con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: creazione e configurazione del documento

Per iniziare, crea un nuovo documento e un oggetto DocumentBuilder associato. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: impostare lo spazio tra il testo asiatico e quello latino

Ora configureremo lo spazio tra testo asiatico e latino utilizzando le proprietà dell'oggetto ParagraphFormat. Ecco come:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Passaggio 3: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Codice sorgente di esempio per spazio tra testo asiatico e latino utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Space Between Asian and Latin Text con Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

Con questo codice sarai in grado di regolare automaticamente lo spazio tra testo asiatico e latino nel tuo documento usando Aspose.Words per .NET.



