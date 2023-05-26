---
title: Codice in linea
linktitle: Codice in linea
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come incorporare il codice con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/inline-code/
---

In questo esempio, ti illustreremo come utilizzare la funzione di codice inline con Aspose.Words per .NET. Il codice in linea viene utilizzato per rappresentare visivamente parti di codice all'interno di un paragrafo.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: aggiungi lo stile per il codice in linea

 Aggiungeremo uno stile personalizzato per il codice in linea utilizzando il`Styles.Add` metodo del`Document` oggetto. In questo esempio, stiamo creando uno stile chiamato "InlineCode" per il codice in linea con un apice inverso predefinito.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Passaggio 3: aggiungi il codice in linea

Ora possiamo aggiungere codice in linea utilizzando lo stile personalizzato "InlineCode". In questo esempio, aggiungiamo due parti di testo con un numero diverso di apici inversi.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Esempio di codice sorgente per codice inline con Aspose.Words per .NET

```csharp
	// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
	DocumentBuilder builder = new DocumentBuilder();

	//Manca il numero di apici inversi, per impostazione predefinita verrà utilizzato un apice inverso.
	Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
	builder.Font.Style = inlineCode1BackTicks;
	builder.Writeln("Text with InlineCode style with 1 backtick");

	// Ci saranno 3 backtick.
	Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
	builder.Font.Style = inlineCode3BackTicks;
	builder.Writeln("Text with InlineCode style with 3 backtick");
            
```

Congratulazioni! Ora hai imparato come utilizzare la funzionalità del codice inline con Aspose.Words per .NET.

