---
title: Sposta nel campo di unione
linktitle: Sposta nel campo di unione
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come implementare la funzione Sposta per unire il campo in Aspose.Words per .NET utilizzando la guida dettagliata.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-merge-field/
---

In questo esempio, esploreremo la funzione Move To Merge Field di Aspose.Words per .NET. Aspose.Words è una potente libreria di manipolazione dei documenti che consente agli sviluppatori di creare, modificare e convertire i documenti di Word a livello di codice. La funzione Sposta per unire campo ci consente di navigare per unire i campi all'interno di un documento ed eseguire varie operazioni su di essi.


## Spiegando il codice sorgente passo dopo passo

Esaminiamo il codice sorgente passo dopo passo per capire come utilizzare la funzione Sposta per unire il campo utilizzando Aspose.Words per .NET.

## Passaggio 1: inizializzazione del documento e del generatore di documenti

Innanzitutto, inizializza gli oggetti Document e DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2 Inserimento di un campo di unione e aggiunta di testo dopo di esso

Utilizzare il metodo InsertField della classe DocumentBuilder per inserire un campo di unione, quindi aggiungere del testo dopo di esso:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Passaggio 3: il cursore del builder si trova attualmente alla fine del documento.

```csharp
Assert.Null(builder.CurrentNode);
```
## Passaggio 4: spostare il cursore del generatore di documenti nel campo di unione

Per spostare il cursore del generatore di documenti nel campo di unione, utilizzare il metodo MoveToField della classe DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Aggiunta di testo subito dopo il campo di unione

Una volta che il cursore del generatore di documenti si trova all'interno del campo di unione, puoi aggiungere del testo subito dopo utilizzando il metodo Write:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Esempio di codice sorgente per Move To Merge Field utilizzando Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci un campo utilizzando DocumentBuilder e aggiungi una sequenza di testo dopo di esso.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Il cursore del builder è attualmente alla fine del documento.
Assert.Null(builder.CurrentNode);
// Possiamo spostare il builder in un campo come questo, posizionando il cursore subito dopo il campo.
builder.MoveToField(field, true);

// Si noti che il cursore si trova in una posizione oltre il nodo FieldEnd del campo, il che significa che non siamo effettivamente all'interno del campo.
// Se desideriamo spostare il DocumentBuilder all'interno di un campo,
// dovremo spostarlo nel nodo FieldStart o FieldSeparator di un campo utilizzando il metodo DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Conclusione

abbiamo esplorato la funzione Move To Merge Field di Aspose.Words per .NET. Abbiamo imparato come navigare per unire i campi all'interno di un documento utilizzando la classe DocumentBuilder ed eseguire operazioni su di essi. Questa funzione è utile durante l'elaborazione di parole a livello di codice con unione

