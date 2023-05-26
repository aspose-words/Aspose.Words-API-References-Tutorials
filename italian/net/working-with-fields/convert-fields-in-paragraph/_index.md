---
title: Converti campi nel paragrafo
linktitle: Converti campi nel paragrafo
second_title: Riferimento all'API Aspose.Words per .NET
description: Converti i campi IF in testo normale in un paragrafo con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/convert-fields-in-paragraph/
---

Ecco un tutorial che illustra come utilizzare la funzione Converti campi in paragrafo con Aspose.Words per .NET. Questo codice converte in testo normale tutti i campi di tipo IF rilevati nell'ultimo paragrafo di un documento. Seguire i passaggi seguenti per comprendere ed eseguire questo codice.

Assicurati di aver installato Aspose.Words per .NET e di configurare il tuo ambiente di sviluppo prima di iniziare.

## Passaggio 1: importa i riferimenti

Per utilizzare Aspose.Words nel tuo progetto, devi aggiungere i riferimenti necessari. Assicurati di aver aggiunto un riferimento alla libreria Aspose.Words nel tuo progetto.

## Passaggio 2: caricamento del documento

Prima di poter convertire i campi, è necessario caricare il documento che contiene i campi da convertire. Assicurati di specificare il percorso corretto della directory contenente il documento. Ecco come caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso effettivo della tua cartella dei documenti.

## Passaggio 3: conversione dei campi in testo

Ora che il documento è caricato, possiamo procedere con la conversione dei campi type in testo normale. In questo esempio, prendiamo di mira solo i campi presenti nell'ultimo paragrafo del documento. Ecco il codice che esegue questa conversione:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Questo codice utilizza una combinazione di metodi LINQ per filtrare i campi nell'ultimo paragrafo del documento e quindi li converte in testo normale chiamando il metodo`Unlink()` metodo.

## Passaggio 4: salvare il documento modificato

 Una volta convertiti i campi, è possibile salvare il documento modificato. Usa il`Save()` metodo per questo. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Assicurarsi di specificare il percorso e il nome file corretti per il backup.

### Esempio di codice sorgente per Converti campi in paragrafo utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento.
Document doc = new Document(dataDir + "Linked fields.docx");

// Converti i campi IF in testo normale nell'ultimo paragrafo del documento.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Salva il documento modificato.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```
