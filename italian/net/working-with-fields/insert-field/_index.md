---
title: Inserisci campo
linktitle: Inserisci campo
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire un campo nei tuoi documenti Word con Aspose.Words per .NET. Personalizza i tuoi documenti con campi dinamici.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-field/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Inserisci un campo" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e di DocumentBuilder

Iniziamo creando un nuovo documento e inizializzando un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: Inserimento del campo

 Noi usiamo il`InsertField()` metodo di DocumentBuilder per inserire un campo nel documento. In questo esempio, inseriamo un campo di unione (MERGEFIELD) con nome campo "MyFieldName" e formato di unione.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Esempio del codice sorgente per l'inserimento di un campo con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci il campo.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inizializzato un DocumentBuilder, quindi inserito un campo di unione con il nome del campo "MyFieldName" e il formato di unione. Il documento viene quindi salvato con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Inserisci un campo" con Aspose.Words per .NET.

### FAQ

#### D: Cos'è un campo in Word?

R: Un campo in Word è un elemento che permette di inserire e manipolare dati dinamici in un documento. Può essere utilizzato per visualizzare informazioni variabili come date, numeri di pagina, tabelle, formule matematiche, ecc.

#### D: Come inserire un campo in un documento Word?

R: Per inserire un campo in un documento Word, puoi seguire questi passaggi:

1. Posiziona il cursore nel punto in cui desideri inserire il campo.
2. Vai alla scheda "Inserisci" nella barra multifunzione.
3. Fare clic sul pulsante "Campo" nel gruppo "Testo" per aprire la finestra di dialogo dei campi.
4. Selezionare il tipo di campo che si desidera inserire dall'elenco a discesa.
5. Configura le opzioni del campo secondo necessità.
6. Fare clic sul pulsante "OK" per inserire il campo nel documento.

#### D: Quali sono i tipi di campo comunemente usati in Word?

R: Word offre un'ampia varietà di tipi di campo che puoi usare nei tuoi documenti. Di seguito sono riportati alcuni dei tipi di campo comunemente utilizzati:

- Data e ora: visualizza la data e l'ora correnti.
- Numero pagina: visualizza il numero della pagina corrente.
- Sommario: genera automaticamente un sommario basato sugli stili dei tuoi titoli.
- Calcolo: esegue calcoli matematici utilizzando formule.
- Testo di riempimento: genera testo casuale per riempire il documento.

#### D: Posso personalizzare l'aspetto dei campi in Word?

R: Sì, puoi personalizzare l'aspetto dei campi in Word utilizzando le opzioni di formattazione disponibili. Ad esempio, puoi modificare il carattere, la dimensione, il colore e lo stile del testo in un campo. Puoi anche applicare effetti di formattazione come grassetto, corsivo e sottolineato.
  