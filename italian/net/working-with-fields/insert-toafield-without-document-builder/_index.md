---
title: Inserisci campo TOA senza Document Builder
linktitle: Inserisci campo TOA senza Document Builder
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo passo per inserire il campo TOA senza Document Builder utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-toafield-without-document-builder/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzione "Inserimento campo TOA" di Aspose.Words per .NET. Segui attentamente ogni passaggio per ottenere i risultati desiderati.

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

## Passaggio 6: Inserimento del campo TOA

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

### Esempio di codice sorgente per l'inserimento di campi TOA senza Document Builder con Aspose.Words per .NET

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
