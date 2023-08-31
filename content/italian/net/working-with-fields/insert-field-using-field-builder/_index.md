---
title: Inserisci campo utilizzando Field Builder
linktitle: Inserisci campo utilizzando Field Builder
second_title: Aspose.Words API di elaborazione dei documenti
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

### FAQ

#### D: Cos'è un costruttore di campo in Aspose.Words?

R: Un Field Builder in Aspose.Words è un potente strumento per creare e manipolare campi in un documento Word. Offre funzionalità avanzate per la creazione e la personalizzazione dei campi, incluso l'inserimento di codici di campo e la gestione delle opzioni di formattazione.

#### D: Quali tipi di campi possono essere inseriti utilizzando il generatore di campi?

R: Il generatore di campi in Aspose.Words ti consente di inserire diversi tipi di campi in un documento Word. Di seguito sono riportati alcuni esempi di tipi di campo comunemente utilizzati:

- MERGEFIELD: utilizzato per unire dati da fonti esterne.
- DATA: visualizza la data corrente.
- PAGINA: visualizza il numero della pagina corrente.
- IF: permette di condizionare la visualizzazione di un contenuto secondo una condizione.
- TOC: genera automaticamente un sommario basato sugli stili del titolo del documento.

#### D: Come personalizzare i campi inseriti con il field builder?

R: Il generatore di campi offre opzioni di personalizzazione per i campi inseriti. È possibile utilizzare i metodi e le proprietà del costruttore di campo per impostare opzioni come la formattazione del campo, gli argomenti, le opzioni e i valori predefiniti. Ad esempio, puoi impostare il formato della data, il formato del numero, il separatore delle migliaia, ecc.
  