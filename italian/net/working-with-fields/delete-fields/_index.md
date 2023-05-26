---
title: Elimina campi
linktitle: Elimina campi
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo passo per l'eliminazione dei campi di unione nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/delete-fields/
---

Per spiegare come utilizzare la funzione "Elimina campi" in Aspose. Words for .NET abbiamo creato una guida passo passo qui sotto. 

È importante seguire attentamente ogni passaggio per ottenere i risultati desiderati. 

## Passaggio 1: creazione di un nuovo documento

In questo frammento di codice iniziamo creando un nuovo documento vuoto utilizzando la seguente riga: 

```csharp
Document doc = new Document();
```

## Passaggio 2: rimuovere i campi di unione

 Per rimuovere tutti i campi di unione presenti nel documento utilizziamo il file`DeleteFields()` funzione. 

Ciò è particolarmente utile se si desidera mantenere solo il contenuto statico e rimuovere qualsiasi informazione di unione. 

### Esempio di codice sorgente per eliminare i campi con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento esistente.
Document doc = new Document(dataDir + "YourDocument.docx");

// Rimuovi i campi di unione.
doc.MailMerge.DeleteFields();

// Salva il documento modificato.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 Nel nostro esempio carichiamo prima un documento esistente prima di chiamare`DeleteFields()`. Infine salviamo il documento modificato con un nuovo nome file. 

Per rimuovere efficacemente i campi di unione da un documento utilizzando Aspose.Words per la funzione "Rimuovi campi" di .NET, prendi spunto da questo esempio. 

Ricorda sempre di sostituire "LA TUA CARTELLA DEI DOCUMENTI" con il tuo percorso di directory specifico. 

Si è così conclusa la nostra guida sull'implementazione della funzionalità "Elimina campi" tramite Aspose.Words per .NET.