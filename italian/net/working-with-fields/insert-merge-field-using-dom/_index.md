---
title: Inserisci campo di unione utilizzando DOM
linktitle: Inserisci campo di unione utilizzando DOM
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire campi di unione di campi personalizzati nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-merge-field-using-dom/
---

Ecco una guida passo passo per spiegare il codice sorgente C # di seguito che utilizza la funzione "Inserisci campo unione campo" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

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

## Passaggio 3: spostare il cursore sul paragrafo

 Noi usiamo il`MoveTo()` metodo del DocumentBuilder per spostare il cursore sul paragrafo dove vogliamo inserire il campo merge field.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Passaggio 4: Inserimento del campo di unione del campo

 Usiamo il DocumentBuilder`InsertField()` metodo per inserire un campo di unione di campi nel paragrafo.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Quindi configuriamo le proprietà del campo di unione del campo specificando le opzioni appropriate, come il nome del campo, il testo prima e dopo il campo e le opzioni di formattazione verticale.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
field. Update();
```

### Esempio di codice sorgente per l'inserimento di un campo di unione di campi con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sposta il cursore sul paragrafo.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Inserisci campo unione campo.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Aggiorna il campo.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

In questo esempio, abbiamo creato un nuovo documento, spostato il cursore sul paragrafo desiderato e quindi inserito un campo di unione di campi nel documento.