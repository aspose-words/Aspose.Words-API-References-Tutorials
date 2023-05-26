---
title: Carica il dizionario di sillabazione per la lingua
linktitle: Carica il dizionario di sillabazione per la lingua
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come caricare un dizionario di sillabazione per una lingua specifica in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

In questo tutorial passo-passo, ti mostreremo come caricare un dizionario di sillabazione per una lingua specifica in Aspose.Words per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo nei tuoi progetti.

Per iniziare, assicurati di avere Aspose.Words per .NET installato e configurato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scarica e installa la libreria dal sito ufficiale.

## Passaggio 1: caricamento del documento

Innanzitutto, carica il tuo documento dalla directory specificata:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Passaggio 2: caricamento del dizionario di sillabazione

Successivamente, apri uno stream nel file del dizionario di sillabazione e salvalo per la lingua desiderata. In questo esempio, carichiamo un dizionario per lo svizzero tedesco (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Assicurati di avere il file del dizionario appropriato nella directory dei dati.

## Passaggio 3: salvare il documento modificato

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

COSÌ ! Hai caricato correttamente un dizionario di sillabazione per una lingua specifica in Aspose.Words per .NET.

### Codice sorgente di esempio per il caricamento del dizionario di sillabazione per una lingua utilizzando Aspose.Words per .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Sentiti libero di utilizzare questo codice nei tuoi progetti e di modificarlo in base alle tue esigenze specifiche.