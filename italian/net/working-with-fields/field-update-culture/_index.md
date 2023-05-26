---
title: Cultura dell'aggiornamento sul campo
linktitle: Cultura dell'aggiornamento sul campo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come aggiornare la cultura del campo nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/field-update-culture/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Field Culture Update" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e del generatore di documenti

Iniziamo creando un nuovo documento e un generatore di documenti.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: Inserimento del campo orario

 Noi usiamo il`InsertField()` metodo per inserire un campo orario nel documento.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Questo inserirà un campo orario nel documento.

## Passaggio 4: configurazione della cultura di aggiornamento del campo

Configuriamo le opzioni del campo per specificare che la cultura dell'aggiornamento del campo deve essere basata sul codice del campo.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Queste opzioni determinano le impostazioni cultura utilizzate per l'aggiornamento dei campi.

### Esempio di codice sorgente per l'aggiornamento della cultura del campo con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il generatore di documenti.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci il campo dell'ora.
builder. InsertField(FieldType.FieldTime, true);

// Configurare la cultura dell'aggiornamento del campo.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Salva il documento.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

In questo esempio, abbiamo creato un nuovo documento, inserito un campo ora e configurato la cultura di aggiornamento del campo. Quindi abbiamo salvato il documento con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Aggiorna cultura del campo" con Aspose.Words per .NET.