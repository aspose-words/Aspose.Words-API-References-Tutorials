---
title: Parole sillabate delle lingue
linktitle: Parole sillabate delle lingue
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come sillabare le parole in diverse lingue nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-hyphenation/hyphenate-words-of-languages/
---

In questo tutorial passo-passo, ti guideremo su come sillabare le parole in diverse lingue nei documenti di Word usando Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: inizializzazione dell'oggetto documento

 Per prima cosa, inizializza il file`Document` oggetto specificando il percorso del documento di origine contenente testo in diverse lingue:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Passaggio 2: salvare i dizionari di sillabazione

Successivamente, salva i dizionari di sillabazione per le diverse lingue che desideri elaborare. In questo esempio registriamo dizionari per l'inglese americano e il tedesco svizzero:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Assicurati di avere i file di dizionario appropriati nella directory dei dati.

## Passaggio 3: elaborazione delle parole mediante sillabazione

 Ora puoi utilizzare le funzioni di sillabazione per elaborare parole in lingue diverse. Puoi usare diversi metodi di`Document` O`DocumentBuilder` seconda delle vostre specifiche esigenze.

```csharp
// Esempio: utilizzo del metodo Hyphenate di DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Passaggio 4: salvare il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

COSÌ ! Hai elaborato correttamente le parole sillabandole in diverse lingue in un documento di Word utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per la sillabazione delle parole utilizzando Aspose.Words per .NET

	```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "German text.docx");

	Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
	Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

	doc.Save(dataDir + "TreatmentByCesure.pdf");
	```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.
