---
title: Inserisci campo avanzato senza generatore di documenti
linktitle: Inserisci campo avanzato senza generatore di documenti
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un campo avanzato nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Inserimento campo avanzato senza DocumentBuilder" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "LA TUA DIRECTORY DOCUMENTI" con il percorso appropriato della directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e del paragrafo

Iniziamo creando un nuovo documento e recuperando il primo paragrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Passo 3: Inserimento dei campi avanzati

 Noi usiamo il`AppendField()` metodo per inserire un campo avanzato nel paragrafo.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Configuriamo poi le varie proprietà del campo avanzato specificando i valori desiderati.

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

Questo conclude la nostra guida su come utilizzare la funzionalità "Inserisci campo avanzato senza DocumentBuilder" con Aspose.Words per .NET.

### Domande frequenti

#### D: Cos'è un campo avanzato in Aspose.Words?

R: Un campo avanzato in Aspose.Words è un tipo speciale di campo che consente di eseguire calcoli, includere condizioni ed eseguire operazioni complesse in un documento di Word. Offre grande flessibilità per creare campi dinamici e personalizzati.

#### D: Come inserire un campo avanzato in un documento di Word senza utilizzare Document Builder in Aspose.Words?

R: Per inserire un campo avanzato in un documento di Word senza utilizzare Document Builder in Aspose.Words, puoi seguire questi passaggi:

1. Importa la classe Document e Field dallo spazio dei nomi Aspose.Words.Fields.
2. Crea un'istanza di Document caricando il tuo documento esistente.
3. Utilizzare il metodo InsertField per inserire un campo avanzato specificando il codice del campo avanzato.
4. Salva il documento.

#### D: Come ottenere il risultato di un campo avanzato in un documento Word?

R: Per ottenere il risultato di un campo avanzato in un documento Word, puoi utilizzare la proprietà Result disponibile nella classe Field. Questa proprietà restituisce il risultato calcolato del campo.

#### D: Posso modificare la formula di un campo avanzato dopo averlo inserito in un documento Word?

R: Sì, puoi modificare la formula di un campo avanzato dopo averlo inserito in un documento Word. Puoi farlo accedendo alla proprietà FieldCode della classe Field e aggiornando la formula modificando il testo della formula.