---
title: Ottieni tipi di parole di revisione
linktitle: Ottieni tipi di parole di revisione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come ottenere tipi di revisione delle parole in un documento Word utilizzando Aspose.Words per .NET. Questa guida passo passo ti aiuta a gestire le revisioni dei documenti in modo efficiente.
type: docs
weight: 10
url: /it/net/working-with-revisions/get-revision-types/
---
## Introduzione

Ti sei mai trovato immerso in un mare di revisioni di documenti, chiedendoti chi ha spostato cosa e quando? Non sei solo. Gestire le revisioni dei documenti può essere un compito noioso, soprattutto quando si ha a che fare con documenti estesi. Ma non preoccuparti! Con Aspose.Words per .NET, puoi facilmente identificare e gestire queste revisioni. In questa guida ti guideremo attraverso un processo passo passo su come ottenere tipi di revisione delle parole in un documento Word utilizzando Aspose.Words per .NET. Quindi allacciatevi le cinture e tuffiamoci!

## Prerequisiti

Prima di sporcarci le mani con del codice, ci sono alcune cose di cui avrai bisogno:

1.  Aspose.Words per .NET Library: se non l'hai già fatto, scaricalo da[Qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: Visual Studio o qualsiasi altro IDE compatibile con .NET.
3. Conoscenza di base di C#: la comprensione del linguaggio di programmazione C# sarà utile.
4.  Un documento Word con revisioni: assicurati di avere un file`.docx`file con modifiche tracciate per testare il codice.

## Importa spazi dei nomi

Per iniziare, dovrai importare gli spazi dei nomi necessari nel tuo progetto C#. Ciò ti consentirà di accedere alle funzionalità fornite da Aspose.Words per .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Revision;
using System;
```

Suddividiamo l'esempio in più passaggi per una migliore comprensione e implementazione.

## Passaggio 1: imposta la directory dei documenti

Per prima cosa, devi definire il percorso della directory dei tuoi documenti. Qui è dove verrà posizionato il tuo documento Word con le revisioni.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della cartella dei documenti.

## Passaggio 2: carica il documento Word

Successivamente, devi caricare il documento Word nel tuo progetto. Questo documento dovrebbe contenere le revisioni che desideri analizzare.

```csharp
Document doc = new Document(dataDir + "Revisions.docx");
```

 Assicurati che il file`Revisions.docx` esiste nella directory specificata.

## Passaggio 3: accedi alla raccolta di paragrafi

Ora che il tuo documento è caricato, devi accedere ai paragrafi all'interno della prima sezione del corpo del documento. Questo ti aiuterà a scorrere ogni paragrafo per verificare la presenza di revisioni.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
```

## Passaggio 4: scorrere i paragrafi e verificare le revisioni

Ecco dove avviene la magia. Potrai scorrere ogni paragrafo e verificare se è stato spostato (eliminato o inserito).

```csharp
for (int i = 0; i < paragraphs.Count; i++)
{
    if (paragraphs[i].IsMoveFromRevision)
        Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
    if (paragraphs[i].IsMoveToRevision)
        Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

 Questo ciclo attraversa ogni paragrafo e utilizza il file`IsMoveFromRevision`E`IsMoveToRevision` proprietà per determinare se il paragrafo è stato spostato (eliminato) o spostato (inserito).

## Conclusione

Ed ecco qua! Con solo poche righe di codice, puoi facilmente identificare i tipi di revisioni nel tuo documento Word utilizzando Aspose.Words per .NET. Questa potente libreria semplifica la gestione delle revisioni dei documenti, consentendoti di concentrarti su attività più importanti. 

## Domande frequenti

### Posso utilizzare Aspose.Words per .NET per tenere traccia delle modifiche apportate da utenti specifici?

Sì, Aspose.Words per .NET fornisce funzionalità per accedere ai dettagli della revisione, incluso l'autore delle modifiche.

### È disponibile una prova gratuita per Aspose.Words per .NET?

 Assolutamente! Puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).

### Come posso applicare una licenza temporanea per Aspose.Words per .NET?

 È possibile richiedere e applicare una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).

### Dove posso trovare una documentazione più dettagliata per Aspose.Words per .NET?

 La documentazione dettagliata è disponibile su[Sito web Aspose](https://reference.aspose.com/words/net/).

### Posso utilizzare Aspose.Words per .NET in un progetto non commerciale?

Sì, Aspose.Words per .NET può essere utilizzato sia in progetti commerciali che non commerciali, ma assicurati di controllare i termini di licenza.