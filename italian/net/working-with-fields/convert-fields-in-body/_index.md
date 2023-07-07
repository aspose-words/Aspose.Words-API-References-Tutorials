---
title: Converti campi nel corpo
linktitle: Converti campi nel corpo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare Aspose.Words per .NET per convertire i campi della pagina in testo nel corpo di un documento di Word.
type: docs
weight: 10
url: /it/net/working-with-fields/convert-fields-in-body/
---

In questo tutorial passo-passo, ti illustreremo come utilizzare la funzione ConvertFieldsInBody di Aspose.Words per .NET utilizzando il codice sorgente C# fornito. Questa funzione consente di convertire campi specifici nel corpo del documento in testo normale, semplificando l'elaborazione dei documenti. Segui i passaggi seguenti per utilizzare questa funzione in modo efficace.

## Passaggio 1: prerequisiti

Prima di iniziare, assicurati di aver installato Aspose.Words per .NET e di avere un documento pronto per l'elaborazione. Assicurati anche di avere il percorso della directory dei tuoi documenti.

## Passaggio 2: caricare il documento

Inizia dichiarando una variabile per il percorso della tua directory dei documenti, quindi usa quella variabile per inizializzare un oggetto Document dal documento specificato. Nel nostro esempio, il documento si chiama "Linked fields.docx".

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Carica il documento
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Passaggio 3: convertire i campi della pagina in testo normale

Ora che il documento è caricato, possiamo passare ai passaggi di conversione. Per convertire i campi della pagina in testo normale nel corpo della prima sezione, puoi utilizzare il file`Range.Fields` metodo per ottenere tutti i campi nell'intervallo specificato, quindi filtrare i campi di tipo`FieldType.FieldPage` . Quindi puoi usare il`ForEach` metodo per scorrere ogni campo e chiamare il metodo`Unlink()` metodo per convertirlo in testo normale.

```csharp
// Passa i parametri appropriati per convertire i campi della pagina in testo normale nel corpo della prima sezione.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Passaggio 4: salvare il documento modificato

 Una volta convertiti i campi della pagina in testo semplice, è possibile salvare il documento modificato utilizzando il file`Save()` metodo e specificando il percorso e il nome del file di output. Nel nostro esempio, lo salviamo come "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Salva il documento modificato
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Esempio di codice sorgente per convertire i campi nel corpo con Aspose.Words per .NET

Ecco l'esempio di codice sorgente completo per convertire i campi nel corpo usando Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Carica il documento
Document doc = new Document(dataDir + "Linked fields.docx");

// Passa i parametri appropriati per convertire i campi della pagina in testo normale nel corpo della prima sezione.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### FAQ

#### D: Aspose.Words è compatibile con diverse versioni di Microsoft Word?

R: Sì, Aspose.Words è compatibile con varie versioni di Microsoft Word, tra cui Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 e Word 2019.

#### D: Aspose.Words può gestire strutture di campo complesse?

R: Assolutamente! Aspose.Words fornisce un ampio supporto per strutture di campo complesse, inclusi campi nidificati, calcoli ed espressioni condizionali. Puoi sfruttare la potente API per lavorare con qualsiasi tipo di struttura del campo.

#### D: Aspose.Words supporta le operazioni di aggiornamento sul campo?

R: Sì, Aspose.Words ti consente di aggiornare i campi in modo programmatico. Puoi facilmente aggiornare i valori dei campi, aggiornare i calcoli ed eseguire altre operazioni relative ai campi utilizzando l'API.

#### D: Posso convertire i campi in testo semplice utilizzando Aspose.Words?

R: Certamente! Aspose.Words fornisce metodi per convertire i campi in testo normale. Questo può essere utile quando è necessario estrarre il contenuto senza alcuna formattazione o funzionalità relativa al campo.

#### D: È possibile generare documenti Word con campi dinamici utilizzando Aspose.Words?

R: Assolutamente! Aspose.Words offre funzionalità robuste per generare documenti Word con campi dinamici. È possibile creare modelli con campi predefiniti e popolarli dinamicamente con i dati, fornendo una soluzione di generazione di documenti flessibile ed efficiente.