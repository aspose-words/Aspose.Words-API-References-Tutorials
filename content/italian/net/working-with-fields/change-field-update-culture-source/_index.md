---
title: Modifica origine cultura aggiornamento campo
linktitle: Modifica origine cultura aggiornamento campo
second_title: API di elaborazione dei documenti Aspose.Words
description: Cambia campo Aggiorna origine cultura, guida dettagliata per modificare l'origine cultura in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/change-field-update-culture-source/
---

In questo tutorial, ti guideremo attraverso il processo di modifica dell'origine della cultura di aggiornamento del campo nei documenti di Word utilizzando Aspose.Words per .NET. Modificando l'origine cultura, è possibile controllare la formattazione della data durante le operazioni di aggiornamento dei campi e di stampa unione. Ti forniremo il codice sorgente C# necessario e le istruzioni dettagliate per raggiungere questo obiettivo.

## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un documento e DocumentBuilder
Per iniziare, crea un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserisci contenuto con impostazioni locali specifiche
Successivamente, imposta la locale su tedesco e inserisci i campi con la formattazione della data:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Nel codice sopra, impostiamo la locale del carattere su tedesco (ID locale 1031) e inseriamo due campi con una formattazione della data specifica.

## Passaggio 3: modificare l'origine della cultura dell'aggiornamento del campo
Per modificare l'origine cultura dell'aggiornamento del campo, utilizzare la classe FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

In questo esempio, impostiamo la cultura utilizzata durante l'aggiornamento del campo affinché venga scelta dalla cultura utilizzata dal campo.

## Passaggio 4: eseguire la stampa unione
Eseguire un'operazione di stampa unione e specificare il valore della data per il campo "Data2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

In questo frammento di codice eseguiamo l'operazione di stampa unione e forniamo un valore DateTime per il campo "Date2".

## Passaggio 5: salva il documento
Salva il documento modificato in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Codice sorgente di esempio per la modifica dell'origine della cultura dell'aggiornamento del campo utilizzando Aspose.Words per .NET
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
Congratulazioni! Hai imparato con successo come modificare l'origine della cultura di aggiornamento del campo nei documenti di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi controllare la lingua utilizzata per la formattazione della data durante le operazioni di aggiornamento dei campi e di stampa unione. Personalizza la fonte della cultura in base alle tue esigenze per garantire dati accurati e coerenti.

### Domande frequenti

#### D: Come posso modificare l'origine della cultura dell'aggiornamento del campo in Aspose.Words per .NET?

 R: Per modificare l'origine della cultura dell'aggiornamento del campo in Aspose.Words per .NET, è possibile utilizzare il file`Document.FieldOptions.CultureSource` proprietà e impostarne il valore su`FieldCultureSource.FieldCode` O`FieldCultureSource.CurrentThread` . Ad esempio, puoi usare`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` per utilizzare la lingua definita nel codice di campo.

#### D: Come posso specificare una cultura specifica per l'aggiornamento dei campi in Aspose.Words per .NET?

 R: Per specificare una cultura specifica per l'aggiornamento dei campi in Aspose.Words per .NET, è possibile utilizzare il file`Document.FieldOptions.FieldUpdateCultureInfo` proprietà e impostare il file`CultureInfo` oggetto corrispondente alla cultura desiderata. Ad esempio, puoi usare`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` per specificare le impostazioni cultura francesi (Francia).

#### D: È possibile disabilitare l'aggiornamento automatico dei campi in Aspose.Words per .NET?

 R: Sì, è possibile disabilitare l'aggiornamento automatico dei campi in Aspose.Words per .NET. Puoi usare il`Document.FieldOptions.UpdateFields` proprietà e impostarla su`false` per impedire l'aggiornamento automatico dei campi. Ciò consente di controllare manualmente l'aggiornamento dei campi secondo necessità.

#### D: Come posso aggiornare manualmente i campi del documento in Aspose.Words per .NET?

 R: Per aggiornare manualmente i campi in un documento in Aspose.Words per .NET, è possibile utilizzare il file`Field.Update` metodo per ciascun campo individualmente. Ad esempio, puoi usare`field.Update()` per aggiornare il campo specifico.