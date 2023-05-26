---
title: Converti campi nel documento
linktitle: Converti campi nel documento
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per convertire i campi del documento in testo utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/convert-fields-in-document/
---

In questo tutorial, ti guideremo passo dopo passo utilizzando la funzione ConvertFieldsInDocument di Aspose.Words per il software .NET. Spiegheremo in dettaglio il codice sorgente C# necessario per questa funzionalità e forniremo esempi di formati di output markdown.

## Passaggio 1: prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Aspose.Words per .NET installato sul computer di sviluppo.
- Un documento di Word contenente i campi collegati che vuoi convertire in testo.
- Una directory di documenti in cui è possibile salvare il documento trasformato.

## Passaggio 2: configurazione dell'ambiente
Assicurati di aver configurato correttamente il tuo ambiente di sviluppo per utilizzare Aspose.Words per .NET. Importa gli spazi dei nomi necessari e imposta il percorso della directory dei documenti.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 3: caricare il documento
 Usa il`Document` class di Aspose.Words per caricare il documento Word contenente i campi collegati che si desidera convertire.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## Passaggio 4: convertire i campi associati in testo
 Usa il`Unlink()` metodo per convertire in testo tutti i campi di tipo "IF" incontrati nel documento. Questo metodo viene utilizzato per trasformare i campi collegati nel loro contenuto testuale.

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## Passaggio 5: salvare il documento trasformato
 Usa il`Save()` metodo per salvare il documento con i campi convertiti in testo nella directory del documento specificata.

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Esempio di codice sorgente per ConvertFieldsInDocument utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione ConvertFieldsInDocument:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

// Passare i parametri appropriati per convertire in testo tutti i campi IF rilevati nel documento (incluse intestazioni e piè di pagina).
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

// Salva il documento con i campi trasformati su disco
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Conclusione
Aspose.Words per la funzione ConvertFieldsInDocument di .NET è un potente strumento per convertire i campi collegati in un documento Word in testo. 