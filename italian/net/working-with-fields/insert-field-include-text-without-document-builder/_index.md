---
title: Inserisci FieldIncludeText senza Document Builder
linktitle: Inserisci FieldIncludeText senza Document Builder
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un campo FieldIncludeText nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Inserisci un campo FieldIncludeText" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e del paragrafo

Iniziamo creando un nuovo documento e inizializzando un paragrafo.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Passaggio 3: Inserimento del campo FieldIncludeText

 Noi usiamo il`AppendField()` metodo per inserire un campo FieldIncludeText nel paragrafo.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Configuriamo quindi le proprietà del campo FieldIncludeText specificando il nome del segnalibro e il nome del file sorgente.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Successivamente, aggiungiamo il paragrafo al corpo del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
fieldIncludeText.Update();
```

### Esempio del codice sorgente per l'inserimento di un campo FieldIncludeText con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il paragrafo.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Inserisci il campo FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inizializzato un paragrafo, inserito un FieldIncludeTexten specificando il nome del segnalibro e il nome del file sorgente e salvato il documento con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Inserisci un FieldIncludeText" con Aspose.Words per .NET.