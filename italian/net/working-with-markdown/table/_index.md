---
title: Tavolo
linktitle: Tavolo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare una tabella con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/table/
---


In questo esempio, ti illustreremo come creare una tabella utilizzando Aspose.Words per .NET. Una tabella è una struttura di dati che organizza le informazioni in righe e colonne.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Passaggio 2: aggiungi celle e dati

 Aggiungeremo celle e dati alla nostra tabella utilizzando il`InsertCell` metodo e il`Writeln` metodo del generatore di documenti.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Codice sorgente di esempio per la creazione di una tabella con Aspose.Words per .NET

```csharp
	// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
	DocumentBuilder builder = new DocumentBuilder();

	// Aggiungi la prima riga.
	builder.InsertCell();
	builder.Writeln("a");
	builder.InsertCell();
	builder.Writeln("b");

	// Aggiungi la seconda riga.
	builder.InsertCell();
	builder.Writeln("c");
	builder.InsertCell();
	builder.Writeln("d");
            
```

Congratulazioni! Ora hai imparato come creare una tabella con Aspose.Words per .NET.
