---
title: Codice campo
linktitle: Codice campo
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida passo passo per ottenere il codice di campo e il risultato del campo nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/field-code/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzione "Ottieni codice campo" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricamento del documento

Il primo passo è caricare il documento in cui vuoi ottenere i codici di campo.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Assicurati di sostituire "Hyperlinks.docx" con il nome del tuo file.

## Passaggio 3: sfoglia i campi del documento

 Usiamo un`foreach` loop per scorrere tutti i campi presenti nel documento.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 Ad ogni iterazione del ciclo, otteniamo il codice di campo utilizzando il`GetFieldCode()` metodo. Memorizziamo anche il risultato del campo in una variabile.

### Esempio di codice sorgente per Ottieni codice campo con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Passa attraverso i campi del documento.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Fai qualcosa con il codice e il risultato del campo.
}
```

In questo esempio, abbiamo caricato un documento e poi abbiamo passato in rassegna tutti i campi presenti nel documento. Ad ogni iterazione, abbiamo ottenuto il codice e il risultato del campo. È possibile aggiungere la propria logica per elaborare il codice e i campi dei risultati secondo necessità.

Questo conclude la nostra guida sull'utilizzo della funzione "Ottieni codice campo" con Aspose.Words per .NET.