---
title: Rileva numerazione con spazi bianchi
linktitle: Rileva numerazione con spazi bianchi
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come rilevare i numeri di elenco con spazi bianchi in Aspose.Words per .NET. Migliora la struttura dei tuoi documenti con facilità.
type: docs
weight: 10
url: /it/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
In questo tutorial, esploreremo il codice sorgente C# fornito per la funzionalità "Rilevamento della numerazione con spazi bianchi" con Aspose.Words per .NET. Questa funzione consente di rilevare e creare elenchi da un documento di testo contenente numeri di elenco seguiti da spazi bianchi.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

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

In questo passaggio, creiamo una stringa di testo che simula un documento di testo contenente numeri di elenco seguiti da spazi bianchi. Utilizziamo diversi delimitatori di elenco come punto, parentesi quadra chiusa, simbolo di pallottola e spazi bianchi.

## Passaggio 3: configurazione delle opzioni di caricamento

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 In questo passaggio, configuriamo le opzioni di caricamento del documento. Creiamo un nuovo`TxtLoadOptions` oggetto e impostare il`DetectNumberingWithWhitespaces` proprietà a`true`. Ciò consentirà ad Aspose.Words di rilevare i numeri di elenco anche se sono seguiti da spazi bianchi.

## Passaggio 4: caricamento del documento e salvataggio

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 In questo passaggio, carichiamo il documento utilizzando la stringa di testo specificata e le opzioni di caricamento. Usiamo un`MemoryStream` per convertire la stringa di testo in un flusso di memoria. Quindi salviamo il documento risultante in formato .docx.

### Esempio di codice sorgente per la funzionalità di rilevamento della numerazione degli spazi bianchi con Aspose.Words per .NET.

```csharp

            
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Crea un documento di testo in chiaro sotto forma di una stringa con parti che possono essere interpretate come liste.
// Al caricamento, le prime tre liste saranno sempre rilevate da Aspose.Words,
// e gli oggetti List verranno creati per loro dopo il caricamento.
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
// per evitare che i paragrafi che iniziano con numeri vengano erroneamente rilevati come liste.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Carica il documento mentre applichi LoadOptions come parametro e verifica il risultato.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Ora puoi eseguire il codice sorgente per caricare il documento di testo contenente i numeri di elenco con spazi bianchi, quindi creare un documento .docx con gli elenchi rilevati. Il file di output verrà salvato nella directory specificata con il nome "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Conclusione
In questo tutorial, abbiamo esplorato la funzionalità di rilevamento della numerazione degli spazi bianchi in Aspose.Words per .NET. Abbiamo imparato a creare elenchi da un documento di testo contenente numeri di elenco seguiti da spazi bianchi.

Questa funzione è estremamente utile per l'elaborazione di documenti contenenti numeri di elenco formattati in modi diversi. Utilizzando le opportune opzioni di caricamento, Aspose.Words è in grado di rilevare questi numeri di lista, anche se sono seguiti da spazi bianchi, e di convertirli in liste strutturate nel documento finale.

L'utilizzo di questa funzione può farti risparmiare tempo e migliorare l'efficienza del tuo flusso di lavoro. Puoi facilmente estrarre informazioni da documenti di testo e convertirle in documenti ben strutturati con elenchi appropriati.

Ricordarsi di considerare le opzioni di caricamento, come la configurazione del rilevamento della composizione degli spazi vuoti, per ottenere i risultati desiderati.

Aspose.Words per .NET offre molte funzionalità avanzate per la manipolazione e la generazione di documenti. Esplorando ulteriormente la documentazione e gli esempi forniti da Aspose.Words, sarai in grado di sfruttare appieno le capacità di questa potente libreria.

Quindi, non esitare a integrare il rilevamento della numerazione degli spazi bianchi nei tuoi progetti Aspose.Words per .NET e sfrutta i suoi vantaggi per creare documenti ben strutturati e leggibili.


