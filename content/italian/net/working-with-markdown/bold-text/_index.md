---
title: Testo grassetto
linktitle: Testo grassetto
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come scrivere in grassetto con Aspose.Words per .NET Guida passo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/bold-text/
---

In questo esempio, ti diremo come scrivere in grassetto con Aspose.Words per .NET. Il testo in grassetto lo rende più visibile e gli dà più risalto.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: testo in grassetto

 Possiamo mettere in grassetto il testo impostando il generatore di documenti`Font.Bold` proprietà a`true`.

```csharp
builder.Font.Bold = true;
```

## Passaggio 3: aggiungi contenuto al documento

 Ora possiamo aggiungere contenuto al documento utilizzando i metodi di creazione di documenti, come ad esempio`Writeln`, che aggiunge una riga di testo.

```csharp
builder.Writeln("This text will be bold");
```

## Esempio di codice sorgente per testo in grassetto utilizzando Aspose.Words per .NET


```csharp
// Utilizza un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Rendi il testo in grassetto.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Congratulazioni! Ora hai imparato come scrivere in grassetto con Aspose.Words per .NET.


### Domande frequenti

#### D: Come posso rendere il testo in grassetto in Aspose.Words?

 A: Per rendere il testo in grassetto in Aspose.Words, puoi usare il`Font.Bold` proprietà del`Run`oggetto. È possibile impostare questa proprietà su`true` al testo specifico in grassetto. Ad esempio, puoi usare`run.Font.Bold=true` per mettere in grassetto il testo all'interno di`Run` oggetto.

#### D: È possibile mettere in grassetto più parti di testo nello stesso paragrafo?

 R: Sì, puoi mettere in grassetto più parti di testo in un singolo paragrafo utilizzando Multiplo`Run` oggetti. Puoi crearne multipli`Run` oggetti e impostare il`Font.Bold` proprietà a`true` per ciascun oggetto per mettere in grassetto le parti di testo desiderate. Quindi puoi aggiungerli al paragrafo usando il`Paragraph.AppendChild(run)` metodo.

#### D: Posso inserire testo in grassetto in una tabella o cella in Aspose.Words?

 R: Sì, puoi mettere in grassetto il testo che si trova in una tabella o cella in Aspose.Words. Puoi passare alla cella o al paragrafo desiderato utilizzando i metodi appropriati e quindi applicare la formattazione in grassetto utilizzando`Font.Bold` proprietà del`Run` O`Paragraph` oggetto.