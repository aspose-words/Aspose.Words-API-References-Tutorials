---
title: Cambia locale
linktitle: Cambia locale
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come modificare le impostazioni locali per la formattazione di data e numero nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/change-locale/
---

In questo tutorial, ti guideremo attraverso il processo di modifica delle impostazioni locali nei documenti di Word utilizzando Aspose.Words per .NET. Modificando le impostazioni locali, è possibile controllare la formattazione di date e numeri durante le operazioni di stampa unione. Ti forniremo il codice sorgente C# necessario e le istruzioni dettagliate per raggiungere questo obiettivo.

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

## Passaggio 2: inserire un campo
Successivamente, inserisci un campo di unione nel documento utilizzando il metodo InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

Nel codice sopra, inseriamo un campo di unione denominato "Data" nel documento.

## Passaggio 3: modificare le impostazioni internazionali
Per modificare le impostazioni locali per la formattazione di data e numeri, è possibile modificare le impostazioni cultura correnti del thread. In questo esempio, imposteremo la lingua tedesca ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

Nel codice sopra, memorizziamo la cultura corrente e quindi impostiamo la cultura del thread corrente su tedesco.

## Passaggio 4: eseguire la stampa unione
Eseguire un'operazione di stampa unione e fornire il valore della data per il campo "Data":

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

In questo frammento di codice, eseguiamo l'operazione di stampa unione e forniamo la data corrente come valore per il campo "Data".

## Passaggio 5: ripristinare le impostazioni locali originali
Al termine della stampa unione, ripristinare le impostazioni cultura originali per il thread:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

Nel codice precedente, ripristiniamo la cultura originale del thread.

## Passaggio 6: salvare il documento
Salvare il documento modificato in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Esempio di codice sorgente per la modifica delle impostazioni locali utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per modificare le impostazioni locali nei documenti di Word utilizzando Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come modificare le impostazioni locali nei documenti di Word utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, ora puoi controllare la formattazione di date e numeri durante le operazioni di stampa unione. Personalizza le impostazioni locali in base alle tue esigenze per garantire una formattazione accurata e coerente nei tuoi documenti.

### FAQ

#### D: Aspose.Words è compatibile con diverse versioni di Microsoft Word?

R: Sì, Aspose.Words è compatibile con diverse versioni di Microsoft Word, tra cui Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 e Word 2019.

#### D: Aspose.Words supporta strutture di campo complesse?

R: Assolutamente! Aspose.Words offre un ampio supporto per strutture di campo complesse, inclusi campi nidificati, calcoli ed espressioni condizionali. Puoi utilizzare questa potente API per lavorare con qualsiasi tipo di struttura del campo.

#### D: Aspose.Words supporta le operazioni di aggiornamento sul campo?

R: Sì, Aspose.Words ti consente di aggiornare i campi in base a una pianificazione. Puoi facilmente aggiornare i valori dei campi, aggiornare i calcoli ed eseguire altre operazioni relative ai campi utilizzando l'API.

#### D: È possibile convertire i campi in testo semplice utilizzando Aspose.Words?

R: Certamente! Aspose.Words fornisce metodi per convertire i campi in testo normale. Ciò può essere utile quando è necessario estrarre il contenuto senza alcuna formattazione o funzionalità relativa al campo.

#### D: È possibile generare documenti Word con campi dinamici utilizzando Aspose.Words?

R: Assolutamente! Aspose.Words offre funzionalità robuste per la generazione di documenti Word con campi dinamici. È possibile creare modelli con campi predefiniti e popolarli dinamicamente con dati, fornendo una soluzione flessibile ed efficiente per la generazione di documenti.