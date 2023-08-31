---
title: Cultura dell'aggiornamento sul campo
linktitle: Cultura dell'aggiornamento sul campo
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiornare la cultura del campo nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/field-update-culture/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Field Culture Update" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e del generatore di documenti

Iniziamo creando un nuovo documento e un generatore di documenti.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: Inserimento del campo orario

 Noi usiamo il`InsertField()` metodo per inserire un campo orario nel documento.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Questo inserirà un campo orario nel documento.

## Passaggio 4: configurazione della cultura di aggiornamento del campo

Configuriamo le opzioni del campo per specificare che la cultura dell'aggiornamento del campo deve essere basata sul codice del campo.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Queste opzioni determinano le impostazioni cultura utilizzate per l'aggiornamento dei campi.

### Esempio di codice sorgente per l'aggiornamento della cultura del campo con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il generatore di documenti.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci il campo dell'ora.
builder. InsertField(FieldType.FieldTime, true);

// Configurare la cultura dell'aggiornamento del campo.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Salva il documento.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

In questo esempio, abbiamo creato un nuovo documento, inserito un campo ora e configurato la cultura di aggiornamento del campo. Quindi abbiamo salvato il documento con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Aggiorna cultura del campo" con Aspose.Words per .NET.

### FAQ

#### D: Qual è la cultura dell'aggiornamento del campo in Aspose.Words?

R: La cultura dell'aggiornamento del campo in Aspose.Words si riferisce alla cultura utilizzata per formattare e aggiornare i valori dei campi in un documento Word. La cultura determina il modo in cui numeri, date e altri dati vengono presentati nei campi quando vengono aggiornati.

#### D: Come impostare la cultura di aggiornamento per i campi in un documento di Word con Aspose.Words?

R: Per impostare la cultura di aggiornamento per i campi in un documento Word con Aspose.Words, puoi seguire questi passaggi:

1. Importa la classe Document dallo spazio dei nomi Aspose.Words.
2. Crea un'istanza di Documento caricando il tuo documento esistente.
3. Utilizzare la proprietà Document.UpdateFieldsCultureInfo per impostare le impostazioni cultura di aggiornamento per i campi.

#### D: Quali sono le culture supportate per l'aggiornamento dei campi in Aspose.Words?

R: Aspose.Words supporta diverse culture per l'aggiornamento dei campi. È possibile specificare qualsiasi lingua supportata dal sistema operativo. Ad esempio, "en-US" per l'inglese americano, "fr-FR" per il francese, "de-DE" per il tedesco, ecc.

#### D: È possibile impostare una cultura specifica per un singolo campo piuttosto che per l'intero documento?

R: Sì, è possibile impostare una cultura specifica per un singolo campo piuttosto che per l'intero documento. In Aspose.Words, ogni campo ha una proprietà Format che può essere utilizzata per impostare le impostazioni cultura di formattazione specifiche per quel campo. Ciò consente di controllare come questo campo viene visualizzato e aggiornato indipendentemente dagli altri campi nel documento.

#### D: Come posso verificare la cultura di aggiornamento del campo attualmente definita in un documento di Word?

R: Per verificare la cultura di aggiornamento del campo attualmente definito in un documento di Word, è possibile utilizzare la proprietà Document.UpdateFieldsCultureInfo. Questa proprietà restituisce l'oggetto CultureInfo che rappresenta le impostazioni cultura attualmente utilizzate per impostare gli aggiornamenti dei campi.