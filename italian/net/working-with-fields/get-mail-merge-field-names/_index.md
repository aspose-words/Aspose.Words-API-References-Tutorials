---
title: Ottieni i nomi dei campi di stampa unione
linktitle: Ottieni i nomi dei campi di stampa unione
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come ottenere i nomi dei campi di stampa unione nei documenti di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/get-mail-merge-field-names/
---

Ecco una guida passo-passo per spiegare il codice sorgente C# di seguito, che utilizza la funzione "Ottieni nomi dei campi di unione" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricamento del documento

Il primo passaggio consiste nel caricare il documento in cui si desidera ottenere i nomi dei campi di unione.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Assicurati di sostituire "IL TUO FILE DOCUMENTO" con il nome del tuo file.

## Passaggio 3: ottieni i nomi dei campi di unione

 Noi usiamo il`GetFieldNames()` metodo per ottenere un array contenente i nomi dei campi di unione presenti nel documento.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 IL`fieldNames` La variabile ora contiene i nomi dei campi di unione.

### Esempio di codice sorgente per ottenere i nomi dei campi di unione con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Ottieni i nomi dei campi di unione.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Visualizza il numero di campi di unione.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 In questo esempio, abbiamo caricato un documento, ottenuto i nomi dei campi di unione utilizzando l'estensione`GetFieldNames()` metodo e visualizzato il numero di campi di unione presenti nel documento.

Questo conclude la nostra guida sull'utilizzo della funzione "Ottieni nomi dei campi di unione" con Aspose.Words per .NET.

### Domande frequenti

#### D1: Cos'è la stampa unione in Aspose.Words?

La stampa unione in Aspose.Words è un processo per unire i dati da una fonte esterna (ad esempio foglio di calcolo Excel o database) con un modello di documento Word per creare documenti personalizzati. Ciò facilita la generazione automatizzata di lettere, relazioni e altri documenti simili.

#### D2: Come si ottiene l'elenco dei campi di stampa unione disponibili in un documento di Word?

Per ottenere l'elenco dei campi di stampa unione disponibili in un documento di Word, puoi seguire questi passaggi:

1. Importare le classi Document e MailMergeFieldNames dallo spazio dei nomi Aspose.Words.
2. Crea un'istanza Documento caricando il tuo documento Word.
3. Utilizzare il metodo GetMailMergeFieldNames dell'oggetto Document per ottenere l'elenco dei campi di stampa unione disponibili.

Ecco un codice di esempio per illustrare il processo:

```csharp
// Importa gli spazi dei nomi necessari
using Aspose.Words;
using Aspose.Words.MailMerging;

// Carica il documento esistente
Document document = new Document("FilePath");

// Ottieni l'elenco dei campi di stampa unione
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Scorri i campi di stampa unione disponibili
foreach (string fieldName in fieldNames)
{
     // Fai qualcosa con il nome del campo
     Console.WriteLine(fieldName);
}
```
### FAQ

#### D: Cos'è la stampa unione in Aspose.Words?

R: La stampa unione in Aspose.Words è un processo per unire i dati da una fonte esterna (ad esempio un foglio di calcolo Excel o un database) con un modello di documento Word per creare documenti personalizzati. Ciò facilita la generazione automatizzata di lettere, relazioni e altri documenti simili.

#### D: Come posso ottenere l'elenco dei campi di stampa unione disponibili in un documento di Word?

R: Per ottenere l'elenco dei campi di stampa unione disponibili in un documento di Word, puoi seguire questi passaggi:

1. Importare le classi Document e MailMergeFieldNames dallo spazio dei nomi Aspose.Words.
2. Crea un'istanza Documento caricando il tuo documento Word.
3. Utilizzare il metodo GetMailMergeFieldNames dell'oggetto Document per ottenere l'elenco dei campi di stampa unione disponibili.

#### D: Posso ottenere campi di stampa unione da un'origine dati esterna come un foglio di calcolo Excel?

R: Sì, puoi ottenere i campi di stampa unione da un'origine dati esterna come un foglio di calcolo Excel. Per questo, puoi utilizzare le funzionalità di associazione dati di Aspose.Words per stabilire una connessione con l'origine dati e ottenere i nomi dei campi disponibili.

#### D: È possibile filtrare i campi di stampa unione in base a determinati criteri?

R: Sì, è possibile filtrare i campi di stampa unione in base a determinati criteri. Puoi utilizzare espressioni regolari o condizioni specifiche per filtrare i campi di stampa unione e ottenere solo quelli che soddisfano i tuoi criteri specifici.

#### D: Come posso manipolare i campi di stampa unione in Aspose.Words?

R: Per manipolare i campi di stampa unione in Aspose.Words, puoi utilizzare i metodi e le proprietà forniti dagli oggetti Document e MailMergeField. È possibile aggiungere, rimuovere o aggiornare i campi di stampa unione, nonché recuperare e modificare i valori associati ai campi.