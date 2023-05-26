---
title: Elenco puntato
linktitle: Elenco puntato
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare un elenco puntato con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/bulleted-list/
---

In questo tutorial, ti diremo come creare un elenco puntato con Aspose.Words per .NET. Un elenco puntato viene utilizzato per elencare gli elementi senza utilizzare la numerazione.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: applicazione di un elenco puntato predefinito

 Possiamo applicare un elenco puntato predefinito utilizzando il generatore di documenti`ApplyBulletDefault` metodo.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Passaggio 3: personalizzazione del formato elenco puntato

 Possiamo personalizzare il formato del punto elenco accedendo alle proprietà di`ListFormat.List.ListLevels[0]`. In questo esempio, usiamo il trattino "-" come punto elenco.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Passaggio 4: aggiunta di elementi all'elenco

 Ora possiamo aggiungere elementi all'elenco puntato utilizzando il generatore di documenti`Writeln` metodo.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Passaggio 5: rimozione del rientro dall'elenco

 Se vogliamo creare una sottolista, possiamo aumentare l'indentazione usando il`ListFormat.ListIndent()` metodo. In questo esempio, stiamo aggiungendo un sottoelenco agli elementi 2a e 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Codice sorgente di esempio per l'elenco puntato utilizzando Aspose.Words per .NET


```csharp
	// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
	DocumentBuilder builder = new DocumentBuilder();

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

Congratulazioni! Ora hai imparato come creare un elenco puntato con Aspose.Words per .NET.

