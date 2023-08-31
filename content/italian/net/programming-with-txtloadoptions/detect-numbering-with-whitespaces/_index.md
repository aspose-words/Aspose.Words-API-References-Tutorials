---
title: Rileva la numerazione con spazi bianchi
linktitle: Rileva la numerazione con spazi bianchi
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come rilevare i numeri dell'elenco con spazi bianchi in Aspose.Words per .NET. Migliora facilmente la struttura dei tuoi documenti.
type: docs
weight: 10
url: /it/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
In questo tutorial esploreremo il codice sorgente C# fornito per la funzionalità "Rilevamento della numerazione con spazi bianchi" con Aspose.Words per .NET. Questa funzionalità consente di rilevare e creare elenchi da un documento di testo contenente numeri di elenco seguiti da spazi bianchi.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: creazione del documento di testo

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

In questo passaggio creiamo una stringa di testo che simula un documento di testo contenente numeri di elenco seguiti da spazi bianchi. Utilizziamo diversi delimitatori di elenco come punto, parentesi destra, simbolo di punto elenco e spazi bianchi.

## Passaggio 3: configurazione delle opzioni di caricamento

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 In questo passaggio configuriamo le opzioni di caricamento del documento. Ne creiamo uno nuovo`TxtLoadOptions` oggetto e impostare il`DetectNumberingWithWhitespaces` proprietà a`true`. Ciò consentirà ad Aspose.Words di rilevare i numeri dell'elenco anche se sono seguiti da spazi bianchi.

## Passaggio 4: caricamento del documento e salvataggio

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 In questo passaggio, carichiamo il documento utilizzando la stringa di testo e le opzioni di caricamento specificate. Usiamo a`MemoryStream` per convertire la stringa di testo in un flusso di memoria. Quindi salviamo il documento risultante in formato .docx.

### Codice sorgente di esempio per la funzionalità di rilevamento della numerazione degli spazi bianchi con Aspose.Words per .NET.

```csharp

            
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Crea un documento di testo normale sotto forma di stringa con parti che possono essere interpretate come elenchi.
// Al momento del caricamento, i primi tre elenchi verranno sempre rilevati da Aspose.Words,
// e gli oggetti Elenco verranno creati per loro dopo il caricamento.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Il quarto elenco, con spazi bianchi tra il numero dell'elenco e il contenuto dell'elemento dell'elenco,
// verrà rilevato come elenco solo se "DetectNumberingWithWhitespaces" in un oggetto LoadOptions è impostato su true,
// per evitare che i paragrafi che iniziano con numeri vengano erroneamente rilevati come elenchi.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Carica il documento applicando LoadOptions come parametro e verifica il risultato.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Ora puoi eseguire il codice sorgente per caricare il documento di testo contenente i numeri dell'elenco con spazi bianchi, quindi creare un documento .docx con gli elenchi rilevati. Il file di output verrà salvato nella directory specificata con il nome "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Conclusione
In questo tutorial, abbiamo esplorato la funzionalità di rilevamento della numerazione degli spazi bianchi in Aspose.Words per .NET. Abbiamo imparato come creare elenchi da un documento di testo contenente numeri di elenco seguiti da spazi bianchi.

Questa funzionalità è estremamente utile per elaborare documenti contenenti numeri di elenco formattati in diversi modi. Utilizzando le opzioni di caricamento appropriate, Aspose.Words è in grado di rilevare questi numeri di elenco, anche se sono seguiti da spazi bianchi, e convertirli in elenchi strutturati nel documento finale.

L'utilizzo di questa funzionalità può farti risparmiare tempo e migliorare l'efficienza del tuo flusso di lavoro. Puoi facilmente estrarre informazioni da documenti di testo e convertirli in documenti ben strutturati con elenchi adeguati.

Ricordarsi di considerare le opzioni di caricamento, come la configurazione del rilevamento della composizione degli spazi vuoti, per ottenere i risultati desiderati.

Aspose.Words per .NET offre molte funzionalità avanzate per la manipolazione e la generazione di documenti. Esplorando ulteriormente la documentazione e gli esempi forniti da Aspose.Words, sarai in grado di sfruttare appieno le capacità di questa potente libreria.

Quindi, non esitare a integrare il rilevamento della numerazione degli spazi bianchi nei tuoi progetti Aspose.Words per .NET e sfruttare i suoi vantaggi per creare documenti ben strutturati e leggibili.


