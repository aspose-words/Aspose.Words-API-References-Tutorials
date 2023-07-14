---
title: Granularità di confronto
linktitle: Granularità di confronto
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri la funzione Confronta granularità di Aspose.Words per .NET che consente di confrontare i documenti carattere per carattere, riportando le modifiche apportate.
type: docs
weight: 10
url: /it/net/compare-documents/comparison-granularity/
---
Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzione Confronta granularità di Aspose.Words per .NET.

## Passaggio 1: Introduzione

La funzione Confronta granularità di Aspose.Words per .NET consente di confrontare i documenti a livello di carattere. Ciò significa che ogni personaggio verrà confrontato e le modifiche verranno riportate di conseguenza.

## Passaggio 2: configurazione dell'ambiente

Prima di iniziare, devi configurare il tuo ambiente di sviluppo per lavorare con Aspose.Words per .NET. Assicurati di aver installato la libreria Aspose.Words e di avere un progetto C# adatto in cui incorporare il codice.

## Passaggio 3: aggiungere gli assembly richiesti

Per utilizzare la funzionalità Confronta granularità di Aspose.Words per .NET, è necessario aggiungere gli assembly necessari al progetto. Assicurati di avere i riferimenti corretti ad Aspose.Words nel tuo progetto.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Passaggio 4: creazione di documenti

In questo passaggio, creeremo due documenti utilizzando la classe DocumentBuilder. Questi documenti saranno utilizzati per il confronto.

```csharp
// Crea il documento A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Crea il documento B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Passaggio 5: configurazione delle opzioni di confronto

In questo passaggio, configureremo le opzioni di confronto per specificare la granularità del confronto. Qui useremo la granularità a livello di carattere.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Passaggio 6: confronto dei documenti

Confrontiamo ora i documenti utilizzando il metodo Compare della classe Document. Le modifiche verranno salvate nel documento A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 IL`Compare`Il metodo confronta il documento A con il documento B e salva le modifiche al documento A. È possibile specificare il nome dell'autore e la data del confronto come riferimento.

## Conclusione

In questo articolo, abbiamo esplorato la funzione Confronta granularità di Aspose.Words per .NET. Questa funzione consente di confrontare i documenti a livello di carattere e segnalare le modifiche. Puoi utilizzare questa conoscenza per eseguire confronti dettagliati dei documenti nei tuoi progetti.

### Esempio di codice sorgente per Comparison Granularity utilizzando Aspose.Words per .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```
