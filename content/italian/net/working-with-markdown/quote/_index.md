---
title: Citazione
linktitle: Citazione
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come utilizzare la citazione con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/quote/
---

In questo esempio, spiegheremo come utilizzare la funzione quote con Aspose. Le parole per .NET Quote vengono utilizzate per evidenziare sezioni di testo circondandole con un bordo speciale.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: utilizzo dello stile di citazione predefinito

Useremo lo stile di paragrafo predefinito chiamato "Citazione" per applicare la formattazione delle virgolette al testo.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Passaggio 3: creazione di stili per livelli nidificati

 Possiamo creare stili per livelli nidificati utilizzando il file`Styles.Add` metodo del`Document` oggetto. In questo esempio, stiamo creando uno stile chiamato "Quote1" per rappresentare un livello di quotazione nidificato.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Esempio di codice sorgente per citazioni con Aspose.Words per .NET


```csharp
// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Per impostazione predefinita, un documento memorizza lo stile blockquote per il primo livello.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Crea stili per livelli nidificati attraverso l'ereditarietà degli stili.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Congratulazioni! Ora hai imparato come utilizzare la funzione di citazioni con Aspose.Words per .NET.


### FAQ

#### D: Cos'è una citazione in Markdown?

R: Una citazione in Markdown è un modo per evidenziare passaggi di testo da altre fonti o per fare riferimento a citazioni famose.

#### D: Come utilizzare le virgolette in Markdown?

R: Per utilizzare una citazione in Markdown, racchiudi il testo della citazione tra parentesi angolari (`>`). Ogni riga della citazione deve iniziare con un gallone.

#### D: Le citazioni di Markdown supportano gli attributi?

R: Le citazioni Markdown non supportano attributi specifici. Sono semplicemente evidenziati dalla formattazione del testo citato.

#### D: Puoi incorporare le virgolette in Markdown?

R: Sì, è possibile nidificare le virgolette in Markdown aggiungendo un ulteriore livello di parentesi angolari (`>`).