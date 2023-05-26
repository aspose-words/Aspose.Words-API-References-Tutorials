---
title: Inserisci campo Nessuno
linktitle: Inserisci campo Nessuno
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un campione AUCUN nei tuoi documenti Word con Aspose.Words pour .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-field-none/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzione "Inserisci campo NONE" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

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

## Passo 3: Inserimento del campo NONE

 Noi usiamo il`InsertField()` metodo di DocumentBuilder per inserire un campo NONE nel documento.

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### Esempio di codice sorgente per l'inserimento di un campo NONE con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci il campo NESSUNO.
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inizializzato un DocumentBuilder e quindi inserito un campo NONE. Il documento viene quindi salvato con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Inserisci campo NONE" con Aspose.Words per .NET.