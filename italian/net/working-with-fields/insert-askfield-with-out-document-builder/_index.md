---
title: Inserisci ASKField senza Document Builder
linktitle: Inserisci ASKField senza Document Builder
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un campo ASK nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzione "Inserisci un campo ASK senza DocumentBuilder" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

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

## Passo 3: Inserimento del campo ASK

 Noi usiamo il`AppendField()` metodo per inserire un campo ASK nel paragrafo.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Configuriamo quindi le varie proprietà del campo ASK specificando i valori desiderati.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
field. Update();
```

### Esempio del codice sorgente per l'inserimento di un campo ASK senza DocumentBuilder con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserisci il campo ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inserito un campo ASK senza utilizzare DocumentBuilder, configurato le varie proprietà del campo e salvato il documento con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Inserisci campo ASK senza DocumentBuilder" con Aspose.Words per .NET.