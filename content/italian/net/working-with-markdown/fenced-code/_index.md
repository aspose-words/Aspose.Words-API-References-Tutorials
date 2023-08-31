---
title: Codice recintato
linktitle: Codice recintato
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare la funzionalità di codice recintato con Aspose.Words per .NET Guida passo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/fenced-code/
---

In questo esempio, ti spiegheremo come utilizzare la funzionalità di codice recintato con Aspose.Words per .NET. il codice protetto viene utilizzato per rappresentare blocchi di codice con formattazione specifica.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: aggiunta di uno stile per il codice protetto

 Aggiungeremo uno stile personalizzato per il codice recintato utilizzando il file`Styles.Add` metodo del`Document` oggetto. In questo esempio, stiamo creando uno stile chiamato "FencedCode" per il codice protetto.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Passaggio 3: aggiunta di codice protetto senza informazioni

Ora possiamo aggiungere un blocco di codice recintato senza stringa di informazioni utilizzando lo stile personalizzato "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Passaggio 4: aggiungi il codice protetto con la stringa informativa

Possiamo anche aggiungere un blocco di codice delimitato con una stringa di informazioni utilizzando un altro stile personalizzato. In questo esempio stiamo creando uno stile chiamato "FencedCode.C#" per rappresentare un blocco di codice C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Codice sorgente di esempio per il codice recintato utilizzando Aspose.Words per .NET

```csharp
// Utilizza un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Domande frequenti

#### D: Cos'è il codice delimitato in Markdown?

R: Il codice delimitato in Markdown è un metodo di formattazione utilizzato per visualizzare il codice in un documento Markdown. Consiste nell'inquadrare il codice con delimitatori specifici.

#### D: Quali sono i vantaggi del codice delimitato in Markdown?

R: Il codice delimitato in Markdown migliora la leggibilità del codice e ne facilita la comprensione per i lettori. Consente inoltre di preservare l'evidenziazione della sintassi in alcuni editor Markdown.

#### D: Qual è la differenza tra codice delimitato e rientrato in Markdown?

R: Il codice delimitato utilizza delimitatori specifici per racchiudere il codice, mentre il codice rientrato prevede il rientro di ogni riga di codice con spazi o tabulazioni.

#### D: Il codice delimitato in Markdown è supportato da tutti gli editor Markdown?

R: Il supporto per il codice delimitato in Markdown può variare a seconda degli editor Markdown. Controlla la documentazione specifica del tuo editore per essere sicuro.

