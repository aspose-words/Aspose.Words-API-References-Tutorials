---
title: Ottieni i nomi dei campi di stampa unione
linktitle: Ottieni i nomi dei campi di stampa unione
second_title: Riferimento all'API Aspose.Words per .NET
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