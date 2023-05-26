---
title: Inserisci campo avanzato senza il generatore di documenti
linktitle: Inserisci campo avanzato senza il generatore di documenti
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un campo avanzato nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzione "Inserimento avanzato di campi senza DocumentBuilder" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e del paragrafo

Iniziamo creando un nuovo documento e recuperando il primo paragrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Passo 3: Inserimento del campo avanzato

 Noi usiamo il`AppendField()`metodo per inserire un campo avanzato nel paragrafo.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Configuriamo quindi le varie proprietà del campo avanzato specificando i valori desiderati.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
field. Update();
```

### Esempio del codice sorgente per l'inserimento di un campo avanzato senza DocumentBuilder con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserisci il campo avanzato.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inserito un campo avanzato senza utilizzare DocumentBuilder, configurato le varie proprietà del campo e salvato il documento con un nome file specificato.

Questo conclude la nostra guida su come utilizzare la funzione "Inserisci campo avanzato senza DocumentBuilder" con Aspose.Words per .NET.

