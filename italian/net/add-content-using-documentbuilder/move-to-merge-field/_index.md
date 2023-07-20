---
title: Sposta per unire il campo nel documento di Word
linktitle: Sposta per unire il campo nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come implementare il campo Sposta per unire nella funzionalità del documento di Word di Aspose.Words per .NET utilizzando la guida passo-passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-merge-field/
---
In questo esempio, esploreremo il campo Sposta per unire nella funzionalità del documento di Word di Aspose.Words per .NET. Aspose.Words è una potente libreria di manipolazione dei documenti che consente agli sviluppatori di creare, modificare e convertire i documenti di Word a livello di programmazione. La funzione Sposta per unire campo ci consente di navigare per unire i campi all'interno di un documento ed eseguire varie operazioni su di essi.


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

### Domande frequenti per spostare per unire il campo nel documento di Word

#### D: Qual è lo scopo della funzione Sposta per unire il campo in Aspose.Words per .NET?

R: La funzione Move To Merge Field in Aspose.Words per .NET consente agli sviluppatori di navigare per unire i campi all'interno di un documento Word ed eseguire varie operazioni su di essi a livello di programmazione. I campi di unione sono segnaposti speciali utilizzati nei documenti di Word per le operazioni di stampa unione.

#### D: Come posso inserire un campo di unione in un documento di Word utilizzando Aspose.Words per .NET?

R: Puoi utilizzare il metodo InsertField della classe DocumentBuilder per inserire un campo di unione nel documento. Dopo aver inserito il campo di unione, è possibile aggiungere contenuto, ad esempio testo, prima o dopo il campo utilizzando il metodo Write.

#### D: Come faccio a spostare il cursore del generatore di documenti su un campo di unione specifico?

R: Per spostare il cursore del generatore di documenti su un campo di unione specifico, utilizzare il metodo MoveToField della classe DocumentBuilder e passare il campo come parametro. Questo posizionerà il cursore immediatamente dopo il campo di unione.

#### D: Posso aggiungere del testo all'interno di un campo unione utilizzando la funzione Sposta in campo unione?

R: No, la funzione Sposta nel campo di unione posiziona il cursore del generatore di documenti subito dopo il campo di unione. Per aggiungere testo all'interno del campo di unione, puoi utilizzare il metodo DocumentBuilder.MoveTo per spostare il cursore sul nodo FieldStart o FieldSeparator del campo di unione.

#### D: Come posso eseguire operazioni di stampa unione utilizzando Aspose.Words per .NET?

R: Aspose.Words per .NET fornisce un ampio supporto per le operazioni di stampa unione. È possibile utilizzare la classe MailMerge per eseguire la stampa unione utilizzando dati provenienti da varie origini, ad esempio matrici, set di dati o origini dati personalizzate.