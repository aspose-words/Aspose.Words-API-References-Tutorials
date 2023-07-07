---
title: Inserisci il campo di blocco dell'indirizzo di stampa unione utilizzando DOM
linktitle: Inserisci il campo di blocco dell'indirizzo di stampa unione utilizzando DOM
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un campo di blocco dell'indirizzo di stampa unione nei documenti di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Ecco una guida passo-passo per spiegare il codice sorgente C# di seguito, che utilizza la funzione "Inserisci campo blocco indirizzi Stampa unione" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

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

## Passaggio 3: spostare il cursore sul paragrafo

 Usiamo il DocumentBuilder`MoveTo()` metodo per spostare il cursore sul paragrafo in cui vogliamo inserire il campo di blocco dell'indirizzo di stampa unione.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Passaggio 4: Inserimento del campo Blocco indirizzo stampa unione

 Usiamo il DocumentBuilder`InsertField()` metodo per inserire un campo di blocco dell'indirizzo di stampa unione nel paragrafo.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Configuriamo quindi le proprietà del campo di blocco dell'indirizzo specificando le opzioni appropriate, come l'inclusione del nome del paese/regione, la formattazione dell'indirizzo in base al paese/regione, i nomi di paese/regione esclusi , il formato del nome e dell'indirizzo e l'identificatore della lingua.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
field. Update();
```

### Esempio di codice sorgente per l'inserimento di un campo di blocco dell'indirizzo di stampa unione con Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Vogliamo inserire un blocco di indirizzi di stampa unione come questo:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { BLOCCO INDIRIZZI \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { BLOCCO INDIRIZZI \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { BLOCCO INDIRIZZI \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { BLOCCO INDIRIZZI \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### FAQ

#### D: Come posso personalizzare il formato dell'indirizzo postale in un documento Word con Aspose.Words per .NET?

 R: È possibile personalizzare il formato dell'indirizzo postale in un documento Word con Aspose.Words per .NET utilizzando le proprietà del`FieldAddressBlock`oggetto. È possibile impostare le opzioni di formattazione come lo stile dell'indirizzo, i separatori, gli elementi facoltativi, ecc. per ottenere il formato desiderato.

#### D: Come posso specificare i dati di origine per il campo dell'indirizzo postale in Aspose.Words per .NET?

 R: Per specificare i dati di origine per il campo dell'indirizzo postale in Aspose.Words per .NET, è possibile utilizzare il`FieldAddressBlock.StartAddress` E`FieldAddressBlock.EndAddress` proprietà. Queste proprietà vengono utilizzate per definire gli intervalli di indirizzi nell'origine dati esterna, ad esempio un file CSV, un database e così via.

#### D: Posso includere elementi facoltativi nel campo dell'indirizzo postale con Aspose.Words per .NET?

 R: Sì, puoi includere elementi facoltativi nel campo dell'indirizzo postale con Aspose.Words per .NET. È possibile definire elementi facoltativi utilizzando il`FieldAddressBlock.OmitOptional` metodo per specificare se includere o escludere elementi facoltativi come il nome del destinatario, il nome dell'azienda, ecc.

#### D: L'inserimento di un campo dell'indirizzo postale utilizzando il DOM influisce sulla struttura del documento di Word con Aspose.Words per .NET?

R: L'inserimento di un campo dell'indirizzo postale utilizzando il DOM non influisce direttamente sulla struttura del documento Word. Tuttavia, aggiunge un nuovo elemento di campo al contenuto del documento. È possibile manipolare la struttura del documento aggiungendo, eliminando o modificando gli elementi esistenti in base alle proprie esigenze.