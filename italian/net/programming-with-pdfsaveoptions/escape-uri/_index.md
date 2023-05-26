---
title: Fuga da Uri
linktitle: Fuga da Uri
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per sfuggire a Uri con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/escape-uri/
---

Questo articolo fornisce una guida passo passo su come utilizzare la funzione di escape Uri con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come inserire collegamenti ipertestuali con Uri escape in un documento.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire la directory dei documenti

 Per iniziare, devi definire il percorso della directory in cui si trovano i tuoi documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un documento e un DocumentBuilder

 Successivamente, dobbiamo creare un nuovo file`Document` oggetto e a`DocumentBuilder` oggetto per costruire il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire collegamenti ipertestuali con Uri sfuggito

 Usa il`InsertHyperlink` metodo del`DocumentBuilder`oggetto per inserire collegamenti ipertestuali nel documento. Uri deve essere sfuggito usando il`Uri.EscapeUriString` funzione per evitare errori di formato.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), falso);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), falso);
```

## Passaggio 4: salva il documento come PDF

 Infine, possiamo salvare il documento come PDF usando il file`Save` metodo del`Document` oggetto. Specificare il nome del file di output.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

È tutto ! Hai inserito correttamente collegamenti ipertestuali con Uri sfuggiti in un documento utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per l'escape di Uri con Aspose.Words per .NET


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", falso);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fil%20test",
		"https://www.google.com/search?q=%2Fthe%20test", falso);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```
