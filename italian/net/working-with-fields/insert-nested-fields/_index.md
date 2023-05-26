---
title: Inserisci campi nidificati
linktitle: Inserisci campi nidificati
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire facilmente campi nidificati nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-nested-fields/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Inserisci campi nidificati" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

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

## Passaggio 3: Inserimento di interruzioni di pagina

Usiamo un loop per inserire più interruzioni di pagina nel documento.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Passaggio 4: passa al piè di pagina

 Noi usiamo il`MoveToHeaderFooter()` metodo di DocumentBuilder per spostare il cursore sul piè di pagina principale.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Passaggio 5: Inserimento del campo nidificato

 Usiamo il DocumentBuilder`InsertField()` metodo per inserire un campo nidificato nel piè di pagina.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
field. Update();
```

### Esempio di codice sorgente per l'inserimento di campi nidificati con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci interruzioni di pagina.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Sposta al piè di pagina.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Inserisci campo nidificato.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Aggiorna il campo.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inserito interruzioni di pagina, spostato il cursore sul piè di pagina e quindi inserito un campo nidificato nel piè di pagina.