---
title: Regola orizzontale
linktitle: Regola orizzontale
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire una regola orizzontale con Aspose.Words per .NET Guida passo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/horizontal-rule/
---

In questo esempio, ti mostreremo come utilizzare la funzionalità della regola orizzontale con Aspose.Words per .NET. La regola orizzontale viene utilizzata per separare visivamente le sezioni di un documento.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: inserimento di una riga orizzontale

 Possiamo inserire una regola orizzontale utilizzando il comando`InsertHorizontalRule` metodo del generatore di documenti.

```csharp
builder. InsertHorizontalRule();
```

## Codice sorgente di esempio per la regola orizzontale con Aspose.Words per .NET

```csharp
// Utilizza un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Inserisci la riga orizzontale.
builder.InsertHorizontalRule();
```

Congratulazioni! Ora hai imparato come utilizzare la funzionalità della regola orizzontale con Aspose.Words per .NET.


### Domande frequenti

#### D: Come posso creare un righello orizzontale in Markdown?

R: Per creare un righello orizzontale in Markdown, puoi utilizzare uno dei seguenti simboli su una riga vuota: tre asterischi (\***), tre trattini (\---), o tre caratteri di sottolineatura (\___).

#### D: Posso personalizzare l'aspetto di un righello orizzontale in Markdown?

R: Nel Markdown standard non è possibile personalizzare l'aspetto dei righelli orizzontali. Tuttavia, alcuni editor ed estensioni Markdown avanzati offrono funzionalità di personalizzazione aggiuntive.

#### D: I righelli orizzontali sono supportati da tutti gli editor Markdown?

R: Sì, gli editor Markdown più popolari supportano i righelli orizzontali. Tuttavia, è sempre meglio controllare la documentazione del fornitore specifico per assicurarsi che sia supportata.

#### D: Quali altri elementi posso creare in Markdown?

R: Oltre ai righelli orizzontali, puoi creare titoli, paragrafi, elenchi, collegamenti, immagini, tabelle e altro in Markdown.