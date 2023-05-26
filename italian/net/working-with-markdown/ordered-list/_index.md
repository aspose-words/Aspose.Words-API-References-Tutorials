---
title: Lista ordinata
linktitle: Lista ordinata
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare un elenco ordinato con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/ordered-list/
---

In questo esempio, spiegheremo come utilizzare la funzionalità dell'elenco ordinato con Aspose.Words per .NET. L'elenco ordinato ti consente di organizzare gli elementi in sequenza con i numeri.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per creare un nuovo documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: applicazione del formato dell'elenco ordinato

Applicheremo il formato dell'elenco ordinato utilizzando il generatore di documenti`ApplyBulletDefault` metodo. Possiamo anche personalizzare il formato della numerazione andando ai livelli dell'elenco e impostando il formato desiderato.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Passaggio 3: aggiunta di elementi all'elenco

 Possiamo aggiungere elementi all'elenco utilizzando il generatore di documenti`Writeln` metodo.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Passaggio 4: rientrare l'elenco

 Possiamo indentare l'elenco usando il generatore di documenti`ListIndent` metodo.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Passaggio 5: salvare il documento

Infine, possiamo salvare il documento nel formato desiderato.

### Codice sorgente di esempio per l'elenco ordinato con Aspose.Words per .NET

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
	builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

Congratulazioni! Ora hai imparato come utilizzare la funzione di elenco ordinato con Aspose.Words per .NET.

