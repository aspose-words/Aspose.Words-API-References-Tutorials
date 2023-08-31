---
title: Sposta nel campo Unisci nel documento di Word
linktitle: Sposta nel campo Unisci nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come implementare la funzionalità Sposta nel campo unisci nella funzione documento Word di Aspose.Words per .NET utilizzando la guida passo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-merge-field/
---
In questo esempio, esploreremo la funzionalità Sposta nel campo unisci nel documento Word di Aspose.Words per .NET. Aspose.Words è una potente libreria di manipolazione di documenti che consente agli sviluppatori di creare, modificare e convertire documenti Word a livello di codice. La funzione Sposta in campo unisci ci consente di navigare per unire i campi all'interno di un documento ed eseguire varie operazioni su di essi.


## Spiegare il codice sorgente passo dopo passo

Esaminiamo passo dopo passo il codice sorgente per capire come utilizzare la funzionalità Sposta nel campo unisci utilizzando Aspose.Words per .NET.

## Passaggio 1: inizializzazione del documento e del generatore di documenti

Innanzitutto, inizializza gli oggetti Document e DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2 Inserimento di un campo unione e aggiunta di testo dopo di esso

Utilizza il metodo InsertField della classe DocumentBuilder per inserire un campo di unione, quindi aggiungi del testo dopo di esso:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Passaggio 3: il cursore del builder è attualmente alla fine del documento.

```csharp
Assert.Null(builder.CurrentNode);
```
## Passaggio 4: spostare il cursore del generatore di documenti sul campo di unione

Per spostare il cursore del generatore di documenti sul campo di unione, utilizza il metodo MoveToField della classe DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Aggiunta di testo immediatamente dopo il campo di unione

Una volta che il cursore del generatore di documenti si trova all'interno del campo di unione, puoi aggiungere testo immediatamente dopo utilizzando il metodo Write:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Codice sorgente di esempio per Move To Merge Field utilizzando Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci un campo utilizzando DocumentBuilder e aggiungi una sequenza di testo dopo di esso.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Il cursore del builder è attualmente alla fine del documento.
Assert.Null(builder.CurrentNode);
// Possiamo spostare il costruttore in un campo come questo, posizionando il cursore immediatamente dopo il campo.
builder.MoveToField(field, true);

// Nota che il cursore si trova in una posizione oltre il nodo FieldEnd del campo, il che significa che non siamo effettivamente all'interno del campo.
// Se desideriamo spostare DocumentBuilder all'interno di un campo,
// dovremo spostarlo nel nodo FieldStart o FieldSeparator di un campo utilizzando il metodo DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Conclusione

abbiamo esplorato la funzionalità Sposta in campo unisci di Aspose.Words per .NET. Abbiamo imparato come navigare per unire i campi all'interno di un documento utilizzando la classe DocumentBuilder ed eseguire operazioni su di essi. Questa funzionalità è utile durante l'elaborazione di parole a livello di codice con unione

### Domande frequenti sullo spostamento per unire il campo nel documento Word

#### D: Qual è lo scopo della funzionalità Sposta nel campo Unisci in Aspose.Words per .NET?

R: La funzionalità Sposta in campo unisci in Aspose.Words per .NET consente agli sviluppatori di navigare per unire i campi all'interno di un documento Word ed eseguire varie operazioni su di essi a livello di codice. I campi di unione sono segnaposto speciali utilizzati nei documenti di Word per le operazioni di stampa unione.

#### D: Come posso inserire un campo di unione in un documento di Word utilizzando Aspose.Words per .NET?

R: Puoi utilizzare il metodo InsertField della classe DocumentBuilder per inserire un campo di unione nel documento. Dopo aver inserito il campo di unione, puoi aggiungere contenuto, ad esempio testo, prima o dopo il campo utilizzando il metodo Write.

#### D: Come posso spostare il cursore del generatore di documenti su un campo di unione specifico?

R: Per spostare il cursore del generatore di documenti su un campo di unione specifico, utilizzare il metodo MoveToField della classe DocumentBuilder e passare il campo come parametro. Ciò posizionerà il cursore immediatamente dopo il campo di unione.

#### D: Posso aggiungere testo all'interno di un campo unione utilizzando la funzione Sposta in campo unione?

R: No, la funzione Sposta nel campo unione posiziona il cursore del generatore di documenti immediatamente dopo il campo unione. Per aggiungere testo all'interno del campo unione, puoi utilizzare il metodo DocumentBuilder.MoveTo per spostare il cursore sul nodo FieldStart o FieldSeparator del campo unione.

#### D: Come posso eseguire operazioni di stampa unione utilizzando Aspose.Words per .NET?

R: Aspose.Words per .NET fornisce un ampio supporto per le operazioni di stampa unione. È possibile utilizzare la classe MailMerge per eseguire la stampa unione utilizzando dati provenienti da varie origini come array, set di dati o origini dati personalizzate.