---
title: Testo in corsivo
linktitle: Testo in corsivo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come scrivere in corsivo con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/italic-text/
---

In questo esempio, ti guideremo attraverso come utilizzare la funzione di testo in corsivo con Aspose.Words per .NET. Il testo in corsivo viene utilizzato per enfatizzare determinate parti di un documento.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: testo in corsivo

 Possiamo scrivere in corsivo il testo impostando i caratteri`Italic` proprietà a`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Codice sorgente di esempio per il testo in corsivo con Aspose.Words per .NET


```csharp
	// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
	DocumentBuilder builder = new DocumentBuilder();

	// Rendi il testo in corsivo.
	builder.Font.Italic = true;
	builder.Writeln("This text will be Italic");
            
```

Congratulazioni! Ora hai imparato come utilizzare la funzione di testo in corsivo con Aspose.Words per .NET.

