---
title: Codice rientrato
linktitle: Codice rientrato
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare il codice indentato con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/indented-code/
---

In questo esempio, spiegheremo come utilizzare la funzione di codice indentato con Aspose.Words per .NET. Il codice indentato viene utilizzato per rappresentare visivamente blocchi di codice con una formattazione specifica.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: aggiungi uno stile per il codice rientrato

 Aggiungeremo uno stile personalizzato per il codice rientrato utilizzando il`Styles.Add` metodo del`Document` oggetto. In questo esempio, stiamo creando uno stile chiamato "IndentedCode" per il codice indentato.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Passaggio 3: aggiungi il codice rientrato

Ora possiamo aggiungere un blocco di codice indentato utilizzando lo stile personalizzato "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Esempio di codice sorgente per codice indentato con Aspose.Words per .NET

```csharp
// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Congratulazioni! Ora hai imparato come utilizzare la funzione di codice rientrato con Aspose.Words per .NET.

