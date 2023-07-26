---
title: Cambia campo Aggiorna origine cultura
linktitle: Cambia campo Aggiorna origine cultura
second_title: Aspose.Words API di elaborazione dei documenti
description: Modifica sorgente cultura aggiornamento campo, guida passo passo per modificare la sorgente cultura in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/change-field-update-culture-source/
---

In questo tutorial, ti guideremo attraverso il processo di modifica dell'origine della cultura dell'aggiornamento del campo nei documenti di Word utilizzando Aspose.Words per .NET. Modificando l'origine delle impostazioni cultura, è possibile controllare la formattazione della data durante le operazioni di aggiornamento dei campi e stampa unione. Ti forniremo il codice sorgente C# necessario e le istruzioni dettagliate per raggiungere questo obiettivo.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un documento e DocumentBuilder
Per iniziare, crea un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire contenuto con impostazioni locali specifiche
Successivamente, imposta le impostazioni locali su tedesco e inserisci i campi con la formattazione della data:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Nel codice sopra, impostiamo il carattere locale su tedesco (ID locale 1031) e inseriamo due campi con una specifica formattazione della data.

## Passaggio 3: modificare l'origine della cultura dell'aggiornamento del campo
Per modificare l'origine della cultura dell'aggiornamento del campo, utilizzare la classe FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

In questo esempio, impostiamo la cultura utilizzata durante l'aggiornamento del campo in modo che sia scelta dalla cultura utilizzata dal campo.

## Passaggio 4: eseguire la stampa unione
Eseguire un'operazione di stampa unione e specificare il valore della data per il campo "Date2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

In questo frammento di codice, eseguiamo l'operazione di stampa unione e forniamo un valore DateTime per il campo "Date2".

## Passaggio 5: salvare il documento
Salvare il documento modificato in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Esempio di codice sorgente per la modifica dell'origine della cultura dell'aggiornamento dei campi utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per modificare l'origine della cultura di aggiornamento del campo nei documenti di Word utilizzando Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come modificare l'origine della cultura di aggiornamento del campo nei documenti di Word utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, è ora possibile controllare la cultura utilizzata per la formattazione della data durante le operazioni di aggiornamento dei campi e stampa unione. Personalizza la fonte della cultura in base alle tue esigenze per garantire una data precisa e coerente.

### FAQ

#### D: Come posso modificare l'origine della cultura di aggiornamento del campo in Aspose.Words per .NET?

 R: Per modificare l'origine della cultura dell'aggiornamento del campo in Aspose.Words per .NET, è possibile utilizzare il file`Document.FieldOptions.CultureSource` property e impostarne il valore a`FieldCultureSource.FieldCode` O`FieldCultureSource.CurrentThread` . Ad esempio, puoi usare`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` per utilizzare la cultura definita nel codice di campo.

#### D: Come posso specificare una cultura specifica per l'aggiornamento dei campi in Aspose.Words per .NET?

R: Per specificare una cultura specifica per l'aggiornamento dei campi in Aspose.Words per .NET, puoi utilizzare il`Document.FieldOptions.FieldUpdateCultureInfo` proprietà e impostare il`CultureInfo` oggetto corrispondente alla cultura desiderata. Ad esempio, puoi usare`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` per specificare le impostazioni cultura francesi (Francia).

#### D: È possibile disabilitare l'aggiornamento automatico dei campi in Aspose.Words per .NET?

 R: Sì, è possibile disabilitare l'aggiornamento automatico dei campi in Aspose.Words per .NET. Puoi usare il`Document.FieldOptions.UpdateFields` proprietà e impostarlo su`false` per impedire l'aggiornamento automatico dei campi. Ciò consente di controllare manualmente l'aggiornamento dei campi secondo necessità.

#### D: Come posso aggiornare manualmente i campi del documento in Aspose.Words per .NET?

 R: Per aggiornare manualmente i campi in un documento in Aspose.Words per .NET, puoi utilizzare il file`Field.Update` metodo per ciascun campo individualmente. Ad esempio, puoi usare`field.Update()` per aggiornare il campo specifico.