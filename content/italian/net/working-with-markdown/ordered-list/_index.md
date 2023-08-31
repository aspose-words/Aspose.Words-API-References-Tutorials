---
title: Lista ordinata
linktitle: Lista ordinata
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare un elenco ordinato con Aspose.Words per .NET Guida passo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/ordered-list/
---

In questo esempio, spiegheremo come utilizzare la funzionalità dell'elenco ordinato con Aspose.Words per .NET. L'elenco ordinato ti consente di organizzare gli elementi in sequenza con i numeri.

## Passaggio 1: utilizzo di un generatore di documenti

Per prima cosa utilizzeremo un generatore di documenti per creare un nuovo documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: applicazione del formato elenco ordinato

 Applicheremo il formato dell'elenco ordinato utilizzando quello del generatore di documenti`ApplyBulletDefault`metodo. Possiamo anche personalizzare il formato della numerazione andando ai livelli dell'elenco e impostando il formato che desideriamo.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Passaggio 3: aggiunta di elementi all'elenco

 Possiamo aggiungere elementi all'elenco utilizzando il generatore di documenti`Writeln` metodo.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Passaggio 4: rientra l'elenco

 Possiamo rientrare l'elenco utilizzando il generatore di documenti`ListIndent` metodo.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Passaggio 5: salvataggio del documento

Infine, possiamo salvare il documento nel formato desiderato.

### Codice sorgente di esempio per elenco ordinato con Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Congratulazioni! Ora hai imparato come utilizzare la funzionalità di elenco ordinato con Aspose.Words per .NET.


### Domande frequenti

#### D: Come creare un elenco ordinato in Markdown?

R: Per creare un elenco ordinato in Markdown, inizia ogni elemento dell'elenco con un numero seguito da un punto (`1.`, `2.`, `3.`), seguito da uno spazio.

#### D: Possiamo nidificare elenchi ordinati in Markdown?

R: Sì, è possibile nidificare elenchi ordinati in Markdown aggiungendo quattro spazi di offset davanti a ciascun elemento dell'elenco nidificato.

#### D: Come personalizzare la numerazione degli elenchi ordinati?

R: Nel Markdown standard, la numerazione dell'elenco ordinato viene generata automaticamente. Tuttavia, alcuni editor Markdown ti consentono di personalizzarlo utilizzando estensioni specifiche.

#### D: Gli elenchi ordinati in Markdown supportano il rientro?

R: Sì, gli elenchi ordinati in Markdown supportano il rientro. Puoi aggiungere uno spostamento a sinistra utilizzando spazi o tabulazioni.

#### D: È possibile aggiungere collegamenti o testo in linea agli elementi dell'elenco?

R: Sì, puoi aggiungere collegamenti o testo in linea agli elementi dell'elenco utilizzando la sintassi Markdown appropriata.