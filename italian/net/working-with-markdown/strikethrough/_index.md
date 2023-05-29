---
title: Barrato
linktitle: Barrato
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come applicare lo stile di testo barrato con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/strikethrough/
---


In questo esempio, ti illustreremo come applicare lo stile di testo barrato utilizzando Aspose.Words per .NET. Il testo barrato viene utilizzato per indicare che il testo è stato eliminato o non è più valido.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: applica lo stile del testo barrato

 Abiliteremo lo stile del testo barrato impostando il`StrikeThrough` proprietà del`Font` opporsi a`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Passaggio 3: aggiungi il testo barrato

 Ora possiamo aggiungere testo barrato utilizzando il generatore di documenti`Writeln` metodo.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Esempio di codice sorgente per testo barrato con Aspose.Words per .NET

```csharp
// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Rendi il testo Barrato.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Congratulazioni! Ora hai imparato come applicare lo stile di testo barrato con Aspose.Words per .NET.
