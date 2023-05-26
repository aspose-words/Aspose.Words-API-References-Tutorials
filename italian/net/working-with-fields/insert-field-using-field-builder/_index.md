---
title: Inserisci campo utilizzando Field Builder
linktitle: Inserisci campo utilizzando Field Builder
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire campi personalizzati nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-field-using-field-builder/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Inserisci un campo utilizzando FieldBuilder" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento

Iniziamo creando un nuovo documento.

```csharp
Document doc = new Document();
```

## Passaggio 3: creazione del campo IF utilizzando FieldBuilder

Usiamo la classe FieldBuilder per costruire un campo IF con due campi MERGEFIELD nidificati. In questo esempio, il campo IF visualizza il nome e il cognome in base a una condizione.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Passo 4: Inserimento del campo IF nel documento

 Noi usiamo il`BuildAndInsert()` metodo per creare e inserire il campo IF in una posizione specifica nel documento.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Codice sorgente di esempio per l'inserimento di un campo utilizzando FieldBuilder con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti.
Document doc = new Document();

// Costruzione del campo IF tramite FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Inserisci il campo IF nel documento.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

In questo esempio, abbiamo creato un nuovo documento, costruito un campo IF con campi MERGEFIELD nidificati e quindi inserito quel campo nel documento in una posizione specificata. Il documento viene quindi salvato con un nome file specifico.
