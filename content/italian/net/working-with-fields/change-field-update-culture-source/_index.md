---
title: Modifica origine cultura aggiornamento campo
linktitle: Modifica origine cultura aggiornamento campo
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come modificare l'origine della cultura dell'aggiornamento del campo in Aspose.Words per .NET con questa guida. Controlla facilmente la formattazione della data in base a culture diverse.
type: docs
weight: 10
url: /it/net/working-with-fields/change-field-update-culture-source/
---
## Introduzione

In questo tutorial, ci immergeremo nel mondo di Aspose.Words per .NET ed esploreremo come modificare l'origine della cultura dell'aggiornamento del campo. Se hai a che fare con documenti Word che includono campi data e devi controllare come queste date vengono formattate in base alle diverse culture, questa guida fa al caso tuo. Esaminiamo il processo passo dopo passo, assicurandoci di comprendere ogni concetto e di poterlo applicare in modo efficace nei tuoi progetti.

## Prerequisiti

Prima di addentrarci nel codice, assicurati di avere quanto segue:

-  Aspose.Words per .NET: puoi scaricarlo da[Qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: qualsiasi IDE compatibile con .NET (ad esempio, Visual Studio).
- Conoscenza di base di C#: questo tutorial presuppone una conoscenza fondamentale della programmazione C#.

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari per il nostro progetto. Ciò garantirà l'accesso a tutte le classi e i metodi richiesti forniti da Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Ora, suddividiamo l'esempio in più passaggi per aiutarti a capire come modificare l'origine della cultura dell'aggiornamento del campo in Aspose.Words per .NET.

## Passaggio 1: inizializzare il documento

 Il primo passo è creare una nuova istanza del file`Document` classe e a`DocumentBuilder`. Ciò pone le basi per costruire e manipolare il nostro documento Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserisci campi con impostazioni internazionali specifiche

Successivamente, dobbiamo inserire i campi nel documento. Per questo esempio, inseriremo due campi data. Imposteremo la locale del carattere su tedesco (LocaleId = 1031) per dimostrare come la lingua influisce sul formato della data.

```csharp
builder.Font.LocaleId = 1031; // tedesco
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

## Passaggio 3: impostare l'origine della cultura dell'aggiornamento del campo

 Per controllare la cultura utilizzata durante l'aggiornamento dei campi, impostiamo il file`FieldUpdateCultureSource` proprietà del`FieldOptions`classe. Questa proprietà determina se la lingua viene presa dal codice di campo o dal documento.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

## Passaggio 4: eseguire la stampa unione

Ora dobbiamo eseguire una stampa unione per popolare i campi con i dati effettivi. In questo esempio, imposteremo il secondo campo data (`Date2`) al 1° gennaio 2011.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

## Passaggio 5: salva il documento

Infine, salviamo il documento nella directory specificata. Questo passaggio completa il processo di modifica dell'origine cultura dell'aggiornamento del campo.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusione

Ed ecco qua! Hai modificato con successo l'origine della cultura dell'aggiornamento del campo in Aspose.Words per .NET. Seguendo questi passaggi puoi assicurarti che i tuoi documenti Word visualizzino date e altri valori di campo in base alle impostazioni cultura specificate. Ciò può essere particolarmente utile quando si generano documenti per un pubblico internazionale.

## Domande frequenti

###  Qual è lo scopo di impostare il file`LocaleId`?
 IL`LocaleId` specifica le impostazioni della lingua per il testo, che influiscono sulla formattazione delle date e di altri dati sensibili alle impostazioni locali.

### Posso utilizzare una lingua diversa dal tedesco?
 Sì, puoi impostare il`LocaleId` qualsiasi identificatore locale valido. Ad esempio, 1033 per l'inglese (Stati Uniti).

###  Cosa succede se non imposto il file`FieldUpdateCultureSource` property?
Se questa proprietà non è impostata, durante l'aggiornamento dei campi verranno utilizzate le impostazioni cultura predefinite del documento.

### È possibile aggiornare i campi in base alla cultura del documento anziché al codice del campo?
 Sì, puoi impostare`FieldUpdateCultureSource` A`FieldUpdateCultureSource.Document` per utilizzare le impostazioni della cultura del documento.

### Come faccio a formattare le date in uno schema diverso?
 È possibile modificare il modello del formato della data nel file`InsertField` metodo modificando il file`\\@` valore di commutazione.