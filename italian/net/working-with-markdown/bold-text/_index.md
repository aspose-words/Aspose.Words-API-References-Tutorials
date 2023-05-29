---
title: Testo grassetto
linktitle: Testo grassetto
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come mettere in grassetto il testo con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/bold-text/
---

In questo esempio, ti diremo come mettere in grassetto il testo con Aspose.Words per .NET. Il testo in grassetto lo rende più visibile e gli conferisce maggiore risalto.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: testo in grassetto

 Possiamo mettere in grassetto il testo impostando il costruttore del documento`Font.Bold` proprietà a`true`.

```csharp
builder.Font.Bold = true;
```

## Passaggio 3: aggiungere contenuto al documento

 Ora possiamo aggiungere contenuto al documento utilizzando i metodi del generatore di documenti, come ad esempio`Writeln`, che aggiunge una riga di testo.

```csharp
builder.Writeln("This text will be bold");
```

## Esempio di codice sorgente per testo in grassetto utilizzando Aspose.Words per .NET


```csharp
// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Rendi il testo in grassetto.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Congratulazioni! Ora hai imparato come mettere in grassetto il testo con Aspose.Words per .NET.


