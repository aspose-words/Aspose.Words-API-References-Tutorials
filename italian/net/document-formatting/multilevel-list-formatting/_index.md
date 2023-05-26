---
title: Formattazione elenco multilivello
linktitle: Formattazione elenco multilivello
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare un elenco multilivello e applicare la formattazione personalizzata con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/multilevel-list-formatting/
---

In questo tutorial, ti mostreremo come utilizzare la funzionalità di formattazione dell'elenco multilivello con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: creazione e configurazione del documento

Per iniziare, crea un nuovo documento e un oggetto DocumentBuilder associato. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: formattazione dell'elenco multilivello

Applicheremo ora la formattazione dell'elenco multilivello utilizzando i metodi disponibili nell'oggetto DocumentBuilder. Ecco come:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Passaggio 3: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Esempio di codice sorgente per la formattazione di elenchi multilivello utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione di formattazione dell'elenco multilivello con Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyNumberDefault();
	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.1");
	builder.Writeln("Item 2.2");
	
	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.2.1");
	builder.Writeln("Item 2.2.2");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 2.3");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 3");

	builder.ListFormat.RemoveNumbers();
	
	doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Con questo codice sarai in grado di creare un elenco a più livelli e applicare la corretta formattazione a ciascun livello utilizzando Aspose.Words per .NET.