---
title: Citazione
linktitle: Citazione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare la citazione con Aspose.Words per .NET Guida passo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/quote/
---

In questo esempio, spiegheremo come utilizzare la funzione di citazione con Aspose.Words per .NET Le citazioni vengono utilizzate per evidenziare sezioni di testo circondandole con un bordo speciale.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: utilizzo dello stile di citazione predefinito

Utilizzeremo lo stile di paragrafo predefinito chiamato "Citazione" per applicare la formattazione delle virgolette al testo.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Passaggio 3: creazione di stili per livelli nidificati

 Possiamo creare stili per livelli nidificati utilizzando il file`Styles.Add` metodo del`Document` oggetto. In questo esempio, stiamo creando uno stile chiamato "Quote1" per rappresentare un livello di quota nidificato.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Codice sorgente di esempio per citazioni con Aspose.Words per .NET


```csharp
// Utilizza un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Per impostazione predefinita, un documento memorizza lo stile delle virgolette per il primo livello.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Crea stili per livelli nidificati tramite l'ereditarietà degli stili.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Congratulazioni! Ora hai imparato come utilizzare la funzionalità delle citazioni con Aspose.Words per .NET.


### Domande frequenti

#### D: Cos'è una citazione in Markdown?

R: Una citazione in Markdown è un modo per evidenziare passaggi di testo provenienti da altre fonti o per fare riferimento a citazioni famose.

#### D: Come utilizzare le virgolette in Markdown?

R: Per utilizzare una citazione in Markdown, racchiudere il testo della citazione tra parentesi angolari (`>`). Ogni riga della citazione deve iniziare con un gallone.

#### D: Le virgolette Markdown supportano gli attributi?

R: Le citazioni Markdown non supportano attributi specifici. Sono semplicemente evidenziati dalla formattazione del testo citato.

#### D: Puoi incorporare virgolette in Markdown?

R: Sì, è possibile nidificare le virgolette in Markdown aggiungendo un ulteriore livello di parentesi angolari (`>`).