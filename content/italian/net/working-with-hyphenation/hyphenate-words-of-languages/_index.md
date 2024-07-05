---
title: Parole con trattino delle lingue
linktitle: Parole con trattino delle lingue
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come sillabare le parole in diverse lingue nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-hyphenation/hyphenate-words-of-languages/
---

In questo tutorial passo passo, ti guideremo su come sillabare le parole in diverse lingue nei documenti Word utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Innanzitutto, inizializza il file`Document` oggetto specificando il percorso del documento di origine contenente testo in diverse lingue:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Passaggio 2: salvataggio dei dizionari di sillabazione

Successivamente, salva i dizionari di sillabazione per le diverse lingue che desideri elaborare. In questo esempio registriamo i dizionari per l'inglese americano e il tedesco svizzero:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Assicurati di avere i file del dizionario appropriati nella directory dei dati.

## Passaggio 3: elaborazione delle parole mediante sillabazione

Ora puoi utilizzare le funzionalità di sillabazione per elaborare parole in diverse lingue. È possibile utilizzare diversi metodi di`Document` O`DocumentBuilder` a seconda delle vostre esigenze specifiche.

```csharp
// Esempio: utilizzo del metodo Sillabazione di DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Passaggio 4: salva il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

COSÌ ! Hai elaborato con successo le parole sillabandole in diverse lingue in un documento Word utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per la sillabazione delle parole utilizzando Aspose.Words per .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e modificarlo per adattarlo alle tue esigenze specifiche.

### Domande frequenti

#### D: Come posso sillabare una parola in una lingua specifica con Aspose.Words?

 R: Per sillabare una parola in una lingua specifica con Aspose.Words, puoi usare il`Hyphenation` classe e il`Hyphenate()` metodo. Crea un'istanza di`Hyphenation` class specificando la lingua desiderata, quindi chiamare la classe`Hyphenate()` metodo che passa la parola da sillabare come argomento. Questo ti darà le sillabe della parola nella lingua specificata.

#### D: Quali codici di lingua devo utilizzare per specificare la lingua di sillabazione in Aspose.Words?

R: Per specificare la lingua di sillabazione in Aspose.Words, è necessario utilizzare i codici lingua appropriati. Ad esempio, puoi utilizzare "en" per l'inglese, "fr" per il francese, "es" per lo spagnolo, "de" per il tedesco, ecc. Consulta la documentazione di Aspose.Words per un elenco completo dei codici di lingua supportati.

#### D: La sillabazione funziona per tutte le lingue in Aspose.Words?

R: La sillabizzazione in Aspose.Words dipende dalle regole di sillabazione specifiche della lingua. Sebbene Aspose.Words supporti un'ampia gamma di lingue, alcune lingue potrebbero non essere supportate o la sillabazione potrebbe non essere disponibile per esse. Controlla la documentazione di Aspose.Words per scoprire quali lingue sono supportate per la sillabizzazione.