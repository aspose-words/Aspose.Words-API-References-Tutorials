---
title: Rileva la numerazione con spazi bianchi
linktitle: Rileva la numerazione con spazi bianchi
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare Aspose.Words per .NET per rilevare la numerazione con spazi bianchi nei documenti di testo normale e garantire che i tuoi elenchi siano riconosciuti correttamente.
type: docs
weight: 10
url: /it/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
## introduzione

Aspose.Words per gli appassionati di .NET! Oggi ci addentreremo in un'affascinante funzionalità che può rendere la gestione degli elenchi nei documenti in chiaro un gioco da ragazzi. Hai mai avuto a che fare con file di testo in cui alcune righe dovrebbero essere elenchi, ma semplicemente non sembrano corrette quando vengono caricate in un documento Word? Bene, abbiamo un bel asso nella manica: rilevare la numerazione con spazi bianchi. Questo tutorial ti guiderà attraverso come utilizzare il file`DetectNumberingWithWhitespaces` opzione in Aspose.Words per .NET per garantire che i tuoi elenchi vengano riconosciuti correttamente, anche quando c'è spazio bianco tra i numeri e il testo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

-  Aspose.Words per .NET: puoi scaricarlo dal file[Rilasci Aspose](https://releases.aspose.com/words/net/) pagina.
- Ambiente di sviluppo: Visual Studio o qualsiasi altro IDE C#.
- .NET Framework installato sul tuo computer.
- Conoscenza di base di C#: comprendere le nozioni di base ti aiuterà a seguire gli esempi.

## Importa spazi dei nomi

Prima di tuffarti nel codice, assicurati di aver importato gli spazi dei nomi necessari nel tuo progetto. Ecco un breve frammento per iniziare:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Loading;
```

Analizziamo il processo in passaggi semplici e gestibili. Ogni passaggio ti guiderà attraverso il codice necessario e spiegherà cosa sta succedendo.

## Passaggio 1: definire la directory dei documenti

Per prima cosa, impostiamo il percorso della directory dei documenti. Qui è dove verranno archiviati i file di input e di output.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un documento di testo normale

Successivamente, creeremo un documento di testo normale come una stringa. Questo documento conterrà parti che possono essere interpretate come elenchi.

```csharp
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
```

## Passaggio 3: configura LoadOptions

 Per rilevare la numerazione con spazi bianchi, dobbiamo impostare il file`DetectNumberingWithWhitespaces` opzione a`true` in un`TxtLoadOptions` oggetto.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

## Passaggio 4: caricare il documento

 Ora carichiamo il documento utilizzando il file`TxtLoadOptions` come parametro. Ciò garantisce che il quarto elenco (con spazi bianchi) venga rilevato correttamente.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

## Passaggio 5: salva il documento

Infine, salva il documento nella directory specificata. Ciò genererà un documento Word con elenchi rilevati correttamente.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

## Conclusione

il gioco è fatto! Con solo poche righe di codice, hai imparato l'arte di rilevare la numerazione con spazi bianchi nei documenti di testo normale utilizzando Aspose.Words per .NET. Questa funzionalità può essere incredibilmente utile quando si ha a che fare con vari formati di testo e si garantisce che gli elenchi siano rappresentati accuratamente nei documenti di Word. Quindi la prossima volta che incontrerai questi elenchi complicati, saprai esattamente cosa fare.

## Domande frequenti

###  Cosa è`DetectNumberingWithWhitespaces` in Aspose.Words for .NET?
`DetectNumberingWithWhitespaces` è un'opzione in`TxtLoadOptions` che consente ad Aspose.Words di riconoscere gli elenchi anche quando sono presenti spazi bianchi tra la numerazione e il testo dell'elemento dell'elenco.

### Posso utilizzare questa funzione per altri delimitatori come punti elenco e parentesi?
 Sì, Aspose.Words rileva automaticamente gli elenchi con delimitatori comuni come punti elenco e parentesi. IL`DetectNumberingWithWhitespaces` aiuta specificamente con gli elenchi che contengono spazi bianchi.

###  Cosa succede se non lo uso`DetectNumberingWithWhitespaces`?
Senza questa opzione, gli elenchi con spazi bianchi tra la numerazione e il testo potrebbero non essere riconosciuti come elenchi e gli elementi potrebbero apparire come semplici paragrafi.

### Questa funzionalità è disponibile in altri prodotti Aspose?
Questa funzionalità specifica è adattata per Aspose.Words per .NET, progettata per gestire l'elaborazione dei documenti Word.

### Come posso ottenere una licenza temporanea per Aspose.Words per .NET?
 È possibile ottenere una licenza temporanea da[Richiedi licenza temporanea](https://purchase.aspose.com/temporary-license/) pagina.

