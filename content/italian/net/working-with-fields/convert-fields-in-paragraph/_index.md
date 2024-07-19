---
title: Converti campi nel paragrafo
linktitle: Converti campi nel paragrafo
second_title: API di elaborazione dei documenti Aspose.Words
description: Converti i campi IF in testo semplice in un paragrafo con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/convert-fields-in-paragraph/
---

Ecco un tutorial che dimostra come utilizzare la funzione Converti campi in paragrafo con Aspose.Words per .NET. Questo codice converte in testo normale tutti i campi di tipo IF incontrati nell'ultimo paragrafo di un documento. Seguire i passaggi seguenti per comprendere ed eseguire questo codice.

Assicurati di aver installato Aspose.Words per .NET e di configurare il tuo ambiente di sviluppo prima di iniziare.

## Passaggio 1: importa i riferimenti

Per utilizzare Aspose.Words nel tuo progetto, devi aggiungere i riferimenti necessari. Assicurati di aver aggiunto un riferimento alla libreria Aspose.Words nel tuo progetto.

## Passaggio 2: caricamento del documento

Prima di poter convertire i campi, è necessario caricare il documento che contiene i campi da convertire. Assicurati di specificare il percorso corretto della directory contenente il documento. Ecco come caricare il documento:

```csharp
//Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Sostituisci "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 3: conversione dei campi in testo

Ora che il documento è caricato, possiamo procedere con la conversione dei campi di tipo in testo semplice. In questo esempio, miriamo solo ai campi presenti nell'ultimo paragrafo del documento. Ecco il codice che esegue questa conversione:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Questo codice utilizza una combinazione di metodi LINQ per filtrare i campi nell'ultimo paragrafo del documento e quindi convertirli in testo semplice chiamando il comando`Unlink()` metodo.

## Passaggio 4: salvataggio del documento modificato

 Una volta convertiti i campi è possibile salvare il documento modificato. Usa il`Save()` metodo per questo. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il backup.

### Esempio di codice sorgente per Converti campi in paragrafo utilizzando Aspose.Words per .NET

```csharp
//Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento.
Document doc = new Document(dataDir + "Linked fields.docx");

// Converti i campi IF in testo semplice nell'ultimo paragrafo del documento.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Salva il documento modificato.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### Domande frequenti

#### D: Cos'è un campo di conversione in Aspose.Words?

R: Un campo di conversione in Aspose.Words è un tipo di campo che converte un valore o un'espressione in un altro formato o tipo di dati. Ad esempio, puoi utilizzare un campo di conversione per convertire una data in un formato specifico, un numero in testo o eseguire altri tipi di conversioni.

#### D: Come inserire un campo di conversione in un paragrafo con Aspose.Words?

R: Per inserire un campo di conversione in un paragrafo con Aspose.Words, puoi seguire questi passaggi:

1. Importa la classe Document dallo spazio dei nomi Aspose.Words.
2. Crea un'istanza di Document caricando il tuo documento esistente.
3. Ottieni il paragrafo in cui desideri inserire il campo di conversione.
4. Utilizzare il metodo InsertField per inserire il campo di conversione con la sintassi corretta.

#### D: Quali formati di conversione supporta Aspose.Words?

R: Aspose.Words supporta un'ampia gamma di formati di conversione nei campi, inclusi formati di data, formati numerici, formati di testo, formati di valuta, formati di percentuale e altro. Puoi controllare la documentazione di Aspose.Words per un elenco completo dei formati di conversione disponibili.

#### D: Come aggiornare un campo di conversione in un documento di Word con Aspose.Words?

R: Per aggiornare un campo di conversione in un documento di Word con Aspose.Words, è possibile utilizzare il metodo UpdateFields. Questo metodo scorre il documento e aggiorna tutti i campi, inclusi i campi di conversione, ricalcolando i valori in base ai dati correnti.