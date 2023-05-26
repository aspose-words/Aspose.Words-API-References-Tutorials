---
title: Inserisci campo
linktitle: Inserisci campo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un campo nei tuoi documenti Word con Aspose.Words per .NET. Personalizza i tuoi documenti con campi dinamici.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-field/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Inserisci un campo" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e di DocumentBuilder

Iniziamo creando un nuovo documento e inizializzando un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: Inserimento del campo

 Noi usiamo il`InsertField()` metodo di DocumentBuilder per inserire un campo nel documento. In questo esempio, inseriamo un campo di unione (MERGEFIELD) con nome campo "MyFieldName" e formato di unione.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Esempio del codice sorgente per l'inserimento di un campo con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci il campo.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inizializzato un DocumentBuilder, quindi inserito un campo di unione con il nome del campo "MyFieldName" e il formato di unione. Il documento viene quindi salvato con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Inserisci un campo" con Aspose.Words per .NET.
