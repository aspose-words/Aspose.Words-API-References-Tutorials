---
title: URI di escape nel documento PDF
linktitle: URI di escape nel documento PDF
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata Come sfuggire all'URI nel documento PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/escape-uri/
---

Questo articolo fornisce una guida passo passo su come sfuggire all'URI nel documento PDF con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come inserire collegamenti ipertestuali con Uri escape in un documento.

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

 Usa il`InsertHyperlink` metodo del`DocumentBuilder` oggetto per inserire collegamenti ipertestuali nel documento. Uri deve essere sfuggito usando il`Uri.EscapeUriString` funzione per evitare errori di formato.

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

## Conclusione

In questo tutorial, abbiamo spiegato come eseguire l'escape degli URI in un documento PDF utilizzando Aspose.Words per .NET. Eseguendo l'escape degli URI, è possibile evitare errori di formattazione e garantire che i collegamenti ipertestuali vengano interpretati e visualizzati correttamente nel documento PDF. Segui i passaggi descritti per inserire collegamenti ipertestuali con URI con caratteri di escape nel tuo documento PDF. Assicurati di scappare.

### Domande frequenti

#### D: Qual è l'URI di escape in un documento PDF e perché è importante?
R: L'URI di escape in un documento PDF si riferisce al metodo di conversione dei caratteri speciali in un URL in sequenze di escape per evitare errori di formato. Questo è importante perché i caratteri speciali in un URL possono interrompere la struttura dell'URL e portare a interpretazioni errate o rendering errato. Eseguendo l'escape dei caratteri speciali, garantiamo che l'URL sia correttamente interpretato e visualizzato nel documento PDF.

#### D: Come posso usare Aspose.Words per .NET per sfuggire agli URI in un documento PDF?
R: Per eseguire l'escape degli URI in un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` oggetto per costruire il documento.

 Usa il`InsertHyperlink` metodo del`DocumentBuilder` oggetto per inserire collegamenti ipertestuali nel documento. Assicurati di eseguire l'escape dell'URI utilizzando il`Uri.EscapeUriString` funzione per evitare errori di formato.

 Usa il`Save` metodo del`Document` oggetto per salvare il documento in formato PDF specificando il nome del file di output.

#### D: Quali sono i vantaggi dell'escape degli URI in un documento PDF?
R: I vantaggi dell'escape dell'URI in un documento PDF sono:

Prevenzione degli errori di formato: l'escape dell'URI aiuta a prevenire gli errori di formato causati da caratteri speciali in un URL, assicurando che l'URL sia correttamente interpretato e visualizzato nel documento PDF.

Compatibilità con i lettori PDF: gli URI con escape sono generalmente ben supportati dai lettori PDF, garantendo una migliore compatibilità e un'esperienza utente coerente.

#### D: Quali caratteri speciali devono essere sottoposti a escape in un URI?
 R: I caratteri speciali che devono essere sottoposti a escape in un URI sono: spazio, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.