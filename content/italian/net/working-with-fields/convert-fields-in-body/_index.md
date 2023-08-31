---
title: Converti campi nel corpo
linktitle: Converti campi nel corpo
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare Aspose.Words per .NET per convertire i campi Pagina in testo nel corpo di un documento Word.
type: docs
weight: 10
url: /it/net/working-with-fields/convert-fields-in-body/
---

In questo tutorial passo passo, ti spiegheremo come utilizzare la funzionalità ConvertFieldsInBody di Aspose.Words per .NET utilizzando il codice sorgente C# fornito. Questa funzionalità ti consente di convertire campi specifici nel corpo del documento in testo semplice, semplificando l'elaborazione dei documenti. Seguire i passaggi seguenti per utilizzare questa funzione in modo efficace.

## Passaggio 1: prerequisiti

Prima di iniziare, assicurati di aver installato Aspose.Words per .NET e di avere un documento pronto per l'elaborazione. Assicurati inoltre di avere il percorso della directory dei tuoi documenti.

## Passaggio 2: caricare il documento

Inizia dichiarando una variabile per il percorso della directory dei documenti, quindi utilizza quella variabile per inizializzare un oggetto Document dal documento specificato. Nel nostro esempio, il documento si chiama "Linked field.docx".

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Passaggio 3: converti i campi della pagina in testo semplice

 Ora che il documento è caricato, possiamo passare ai passaggi della conversione. Per convertire i campi della pagina in testo semplice nel corpo della prima sezione, puoi utilizzare il file`Range.Fields` per ottenere tutti i campi nell'intervallo specificato e quindi filtrare i campi di tipo`FieldType.FieldPage` . Quindi puoi usare il`ForEach` per scorrere ogni campo e chiamare il metodo`Unlink()` metodo per convertirlo in testo semplice.

```csharp
// Passa i parametri appropriati per convertire i campi della pagina in testo semplice nel corpo della prima sezione.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Passaggio 4: salva il documento modificato

Dopo aver convertito i campi della pagina in testo semplice, puoi salvare il documento modificato utilizzando il file`Save()` metodo e specificando il percorso e il nome del file di output. Nel nostro esempio, lo salviamo come "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Salva il documento modificato
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Codice sorgente di esempio per convertire i campi nel corpo con Aspose.Words per .NET

Ecco l'esempio di codice sorgente completo per convertire i campi nel corpo utilizzando Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Linked fields.docx");

// Passa i parametri appropriati per convertire i campi della pagina in testo semplice nel corpo della prima sezione.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Domande frequenti

#### D: Aspose.Words è compatibile con diverse versioni di Microsoft Word?

R: Sì, Aspose.Words è compatibile con varie versioni di Microsoft Word, tra cui Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 e Word 2019.

#### D: Aspose.Words può gestire strutture di campi complesse?

R: Assolutamente! Aspose.Words fornisce un ampio supporto per strutture di campi complesse, inclusi campi nidificati, calcoli ed espressioni condizionali. Puoi sfruttare la potente API per lavorare con qualsiasi tipo di struttura di campo.

#### D: Aspose.Words supporta le operazioni di aggiornamento sul campo?

R: Sì, Aspose.Words ti consente di aggiornare i campi a livello di codice. Puoi aggiornare facilmente i valori dei campi, aggiornare i calcoli ed eseguire altre operazioni relative ai campi utilizzando l'API.

#### D: Posso convertire i campi in testo semplice utilizzando Aspose.Words?

R: Certamente! Aspose.Words fornisce metodi per convertire i campi in testo semplice. Ciò può essere utile quando è necessario estrarre il contenuto senza alcuna formattazione o funzionalità relativa ai campi.

#### D: È possibile generare documenti Word con campi dinamici utilizzando Aspose.Words?

R: Assolutamente! Aspose.Words offre robuste funzionalità per generare documenti Word con campi dinamici. Puoi creare modelli con campi predefiniti e compilarli con dati in modo dinamico, fornendo una soluzione di generazione di documenti flessibile ed efficiente.