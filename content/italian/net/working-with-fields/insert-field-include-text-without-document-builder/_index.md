---
title: Inserisci campo Includi testo senza generatore di documenti
linktitle: Inserisci FieldIncludeText senza Document Builder
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un campo FieldIncludeText nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Inserisci un campo FieldIncludeText" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "LA TUA DIRECTORY DOCUMENTI" con il percorso appropriato della directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e del paragrafo

Iniziamo creando un nuovo documento e inizializzando un paragrafo.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Passaggio 3: inserimento del campo FieldIncludeText

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

In questo esempio, abbiamo creato un nuovo documento, inizializzato un paragrafo, inserito un FieldIncludeTexten specificando il nome del segnalibro e il nome del file di origine e salvato il documento con un nome di file specificato.

Questo conclude la nostra guida sull'utilizzo della funzionalità "Inserisci un FieldIncludeText" con Aspose.Words per .NET.

### Domande frequenti

#### D: Come posso specificare il file sorgente per il campo di inclusione del testo in Aspose.Words per .NET?

 A: Per specificare il file di origine per il campo di inclusione del testo in Aspose.Words per .NET, è possibile utilizzare il`FieldIncludeText.SourceFullName`proprietà per impostare il percorso completo del file di origine. Assicurati che il file sorgente sia accessibile e contenga il contenuto che desideri includere nel campo di inclusione del testo.

#### D: Posso includere testo da una macro nel campo di inclusione del testo con Aspose.Words per .NET?

 R: Sì, puoi includere testo da una macro nel campo di inclusione del testo con Aspose.Words per .NET. Puoi usare il`FieldIncludeText.IncludeText` proprietà per specificare il nome della macro il cui contenuto deve essere incluso nel campo.

#### D: L'inserimento di un campo include testo senza il generatore di documenti influisce sulla struttura del documento Word con Aspose.Words per .NET?

R: L'inserimento di un campo di inclusione testo senza il generatore di documenti non influisce direttamente sulla struttura del documento Word. Tuttavia, aggiunge un nuovo elemento campo al contenuto del documento. Puoi manipolare la struttura del documento aggiungendo, eliminando o modificando gli elementi esistenti in base alle tue esigenze.

#### D: Posso personalizzare l'aspetto del campo di inclusione del testo in un documento di Word con Aspose.Words per .NET?

R: Il campo di inclusione del testo non personalizza direttamente il suo aspetto in un documento Word. Tuttavia, è possibile formattare il testo incluso utilizzando le proprietà del paragrafo, le proprietà del carattere e altri oggetti di formattazione disponibili in Aspose.Words per .NET.