---
title: Inserisci ASKField senza Document Builder
linktitle: Inserisci ASKField senza Document Builder
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un campo ASK nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzione "Inserisci un campo ASK senza DocumentBuilder" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e del paragrafo

Iniziamo creando un nuovo documento e recuperando il primo paragrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Passo 3: Inserimento del campo ASK

 Noi usiamo il`AppendField()` metodo per inserire un campo ASK nel paragrafo.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Configuriamo quindi le varie proprietà del campo ASK specificando i valori desiderati.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
field. Update();
```

### Esempio del codice sorgente per l'inserimento di un campo ASK senza DocumentBuilder con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserisci il campo ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inserito un campo ASK senza utilizzare DocumentBuilder, configurato le varie proprietà del campo e salvato il documento con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Inserisci campo ASK senza DocumentBuilder" con Aspose.Words per .NET.

### FAQ

#### D: Cos'è un campo ASK in Aspose.Words?

R: Un campo ASK in Aspose.Words viene utilizzato per porre all'utente una domanda all'apertura di un documento. Viene spesso utilizzato per richiedere informazioni o feedback specifici che possono variare da utente a utente.

#### D: Come inserire il campo ASK nel documento Word senza utilizzare Document Builder in Aspose.Words?

R: Per inserire un campo ASK in un documento Word senza utilizzare Document Builder in Aspose.Words, puoi seguire questi passaggi:

1. Importa la classe Document e Field dallo spazio dei nomi Aspose.Words.Fields.
2. Crea un'istanza di Documento caricando il tuo documento esistente.
3. Utilizzare il metodo InsertField per inserire un campo ASK specificando il nome della domanda.
4. Salva il documento.

#### D: Come ottengo la risposta dell'utente per un campo ASK in un documento Word?

R: Per ottenere la risposta dell'utente per un campo ASK in un documento Word, puoi utilizzare il metodo GetFieldNames disponibile nella classe Document. Questo metodo restituisce un elenco dei nomi dei campi presenti nel documento. È quindi possibile verificare se il nome del campo ASK è presente nell'elenco e recuperare la risposta associata.

#### D: Il campo ASK può essere utilizzato per richiedere maggiori informazioni all'utente?

R: Sì, il campo ASK può essere utilizzato per richiedere più informazioni all'utente. Puoi inserire più campi ASK nel tuo documento, ciascuno con una domanda diversa. Quando il documento viene aperto, all'utente verranno richieste le risposte corrispondenti.