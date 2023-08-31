---
title: Elimina campi
linktitle: Elimina campi
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per eliminare i campi di unione nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/delete-fields/
---

Spiegare come utilizzare la funzione "Elimina campi" in Aspose. Words per .NET abbiamo creato una guida passo passo di seguito. 

È importante seguire attentamente ogni passaggio per ottenere i risultati desiderati. 

## Passaggio 1: creazione di un nuovo documento

In questo frammento di codice iniziamo creando un nuovo documento vuoto utilizzando la seguente riga: 

```csharp
Document doc = new Document();
```

## Passaggio 2: rimuovi i campi unione

 Per rimuovere tutti i campi unione presenti nel documento utilizziamo il file`DeleteFields()` funzione. 

Ciò è particolarmente utile se desideri mantenere solo il contenuto statico e rimuovere eventuali informazioni di unione. 

### Esempio di codice sorgente per eliminare campi con Aspose.Words per .NET

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

 Nel nostro esempio carichiamo innanzitutto un documento esistente prima di chiamare`DeleteFields()`. Infine salviamo il documento modificato con un nuovo nome file. 

Per rimuovere in modo efficace i campi di unione da un documento utilizzando la funzione "Rimuovi campi" di Aspose.Words per .NET, prendi spunto da questo esempio. 

Ricorda sempre di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso della directory specifica. 

Si è così conclusa la nostra guida sull'implementazione della funzionalità "Elimina campi" tramite Aspose.Words per .NET.

### Domande frequenti

#### D: Cos'è un campo in Aspose.Words?

R: Un campo in Aspose.Words è una struttura di documento che rappresenta un testo generato automaticamente o un valore calcolato. I campi vengono utilizzati per visualizzare informazioni dinamiche in un documento, come numeri di pagina, date, campi di stampa unione, ecc.

#### D: Come eliminare un campo in un documento Word con Aspose.Words?

R: Per eliminare un campo in un documento di Word con Aspose.Words, puoi seguire questi passaggi:

1. Importa la classe Document dallo spazio dei nomi Aspose.Words.
2. Crea un'istanza di Document caricando il tuo documento esistente.
3. Utilizzare il metodo RemoveFields per rimuovere tutti i campi dal documento.

#### D: Posso eliminare campi specifici anziché eliminare tutti i campi da un documento?

R: Sì, puoi eliminare campi specifici anziché eliminare tutti i campi da un documento. Per fare ciò, è necessario accedere a ciascun campo singolarmente e utilizzare il metodo Rimuovi per rimuoverlo.

#### D: Come posso verificare se un campo esiste in un documento Word prima di eliminarlo?

R: Per verificare se un campo esiste in un documento Word prima di eliminarlo, puoi utilizzare il metodo Contiene della raccolta Fields per trovare il campo specificato. Questo metodo restituisce un valore booleano che indica se il campo esiste o meno.

#### D: Quali sono gli effetti dell'eliminazione di un campo sul resto del documento?

R: Quando elimini un campo in un documento Word, il campo viene rimosso dal documento e il testo generato o il valore calcolato associato al campo viene eliminato. Ciò potrebbe influire sul layout del documento, poiché il contenuto generato dal campo verrà eliminato.