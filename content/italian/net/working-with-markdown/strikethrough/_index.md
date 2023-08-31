---
title: Barrato
linktitle: Barrato
second_title: Aspose.Words API di elaborazione dei documenti
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

### FAQ

#### D: Come posso aggiungere il testo barrato in Aspose.Words?

 A: Per aggiungere il testo barrato in Aspose.Words, puoi usare il`Font.StrikeThrough` proprietà del`Run`oggetto. Puoi impostare questa proprietà su`true` per aggiungere testo barrato a un testo specifico. Ad esempio, puoi usare`run.Font.StrikeThrough=true` per aggiungere il testo barrato nel file`Run` oggetto.

#### D: È possibile aggiungere il testo barrato a più parti di testo nello stesso paragrafo?

 R: Sì, puoi aggiungere testo barrato a più parti di testo in un singolo paragrafo utilizzando multiple`Run` oggetti. Puoi creare più file`Run` oggetti e impostare il`Font.StrikeThrough` proprietà a`true`per ogni oggetto per aggiungere il testo barrato alle parti di testo desiderate. Quindi puoi aggiungerli al paragrafo usando il`Paragraph.AppendChild(run)` metodo.

#### D: Posso aggiungere testo barrato al testo che si trova in una tabella o in una cella in Aspose.Words?

 A: Sì, puoi aggiungere testo barrato al testo che si trova in una tabella o in una cella in Aspose.Words. Puoi saltare alla cella o al paragrafo che desideri utilizzando i metodi appropriati e quindi applicare la formattazione del testo barrato utilizzando il`Font.StrikeThrough` proprietà del`Run` O`Paragraph` oggetto.