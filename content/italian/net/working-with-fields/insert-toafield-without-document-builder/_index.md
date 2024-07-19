---
title: Inserisci campo TOA senza generatore di documenti
linktitle: Inserisci campo TOA senza generatore di documenti
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per inserire il campo TOA senza Document Builder utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-toafield-without-document-builder/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "TOA Field Insertion" di Aspose.Words per .NET. Segui attentamente ogni passaggio per ottenere i risultati desiderati.

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

## Passo 3: Inserimento del campo TA

Usiamo la classe FieldTA per inserire un campo TA nel paragrafo.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Passaggio 4: aggiunta del paragrafo al corpo del documento

Aggiungiamo il paragrafo contenente il campo TA al corpo del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Passaggio 5: creazione del paragrafo per il campo TOA

Creiamo un nuovo paragrafo per il campo TOA.

```csharp
para = new Paragraph(doc);
```

## Passo 6: Inserimento del campo TOA

Usiamo la classe FieldToa per inserire un campo TOA nel paragrafo.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Passaggio 7: aggiunta del paragrafo al corpo del documento

Aggiungiamo il paragrafo contenente il campo TOA al corpo del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Passaggio 8: aggiorna il campo TOA

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo TOA.

```csharp
fieldToa.Update();
```

### Esempio di codice sorgente per l'inserimento del campo TOA senza Document Builder con Aspose.Words per .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Vogliamo inserire i campi TA e TOA in questo modo:
// { TA \c 1 \l "Valore 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### Domande frequenti

#### D: Come personalizzare l'aspetto del campo TOA inserito nel documento Word con Aspose.Words per .NET?

 R: Puoi personalizzare l'aspetto del campo TOA inserito utilizzando le proprietà del file`FieldTOA` oggetto per specificare le opzioni di formattazione.

#### D: Posso aggiungere più campi TOA in un singolo documento Word utilizzando Aspose.Words per .NET?

R: Sì, puoi aggiungere più campi TOA in un singolo documento Word utilizzando Aspose.Words per .NET. Basta ripetere i passaggi di inserimento per ciascun campo.

#### D: Come posso verificare se un campo TOA è stato inserito correttamente in un documento Word con Aspose.Words per .NET?

R: Per verificare se un campo TOA è stato inserito correttamente, puoi sfogliare il contenuto del documento e cercare istanze del campo TOA.

#### D: L'inserimento di un campo TOA senza utilizzare DocumentBuilder influisce sulla formattazione del documento Word con Aspose.Words per .NET?

R: L'inserimento di un campo TOA senza utilizzare DocumentBuilder non influisce direttamente sulla formattazione del documento Word. Tuttavia, le opzioni di formattazione del campo TOA possono influire sulla formattazione complessiva del documento.