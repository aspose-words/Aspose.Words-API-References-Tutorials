---
title: Granularità di confronto nel documento di Word
linktitle: Granularità di confronto nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Impara a confrontare la granularità nella funzionalità del documento word di Aspose.Words per .NET che consente di confrontare i documenti carattere per carattere, riportando le modifiche apportate.
type: docs
weight: 10
url: /it/net/compare-documents/comparison-granularity/
---
Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzione Confronta granularità nel documento word di Aspose.Words per .NET.

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

 IL`Compare` Il metodo confronta il documento A con il documento B e salva le modifiche al documento A. È possibile specificare il nome dell'autore e la data del confronto come riferimento.

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

## Conclusione

In questo tutorial, abbiamo esplorato la funzione Comparison Granularity di Aspose.Words per .NET. Questa funzione consente di specificare il livello di dettaglio durante il confronto dei documenti. Scegliendo diversi livelli di granularità, puoi eseguire confronti dettagliati a livello di carattere, parola o blocco, a seconda delle tue esigenze specifiche. Aspose.Words per .NET fornisce una capacità di confronto dei documenti flessibile e potente, facilitando l'identificazione delle differenze nei documenti con diversi livelli di granularità.

### FAQ

#### D: Qual è lo scopo dell'utilizzo della granularità di confronto in Aspose.Words per .NET?

R: La granularità del confronto in Aspose.Words per .NET consente di specificare il livello di dettaglio durante il confronto dei documenti. Con questa funzione, puoi confrontare documenti a diversi livelli, ad esempio a livello di carattere, a livello di parola o persino a livello di blocco. Ogni livello di granularità fornisce un diverso livello di dettaglio nei risultati del confronto.

#### D: Come utilizzo la granularità di confronto in Aspose.Words per .NET?

R: Per utilizzare la granularità di confronto in Aspose.Words per .NET, attenersi alla seguente procedura:
1. Imposta il tuo ambiente di sviluppo con la libreria Aspose.Words.
2. Aggiungi gli assembly necessari al tuo progetto facendo riferimento ad Aspose.Words.
3.  Creare i documenti che si desidera confrontare utilizzando il file`DocumentBuilder` classe.
4.  Configura le opzioni di confronto creando un file`CompareOptions` oggetto e l'impostazione del`Granularity` proprietà al livello desiderato (ad es.`Granularity.CharLevel` per il confronto a livello di carattere).
5.  Usa il`Compare` metodo su un documento, passando l'altro documento e il file`CompareOptions` oggetto come parametri. Questo metodo confronterà i documenti in base alla granularità specificata e salverà le modifiche nel primo documento.

#### D: Quali sono i livelli disponibili di granularità di confronto in Aspose.Words per .NET?

R: Aspose.Words per .NET fornisce tre livelli di granularità di confronto:
- `Granularity.CharLevel`: confronta i documenti a livello di carattere.
- `Granularity.WordLevel`: confronta i documenti a livello di parola.
- `Granularity.BlockLevel`: confronta i documenti a livello di blocco.

#### D: Come posso interpretare i risultati del confronto con la granularità a livello di carattere?

R: Con la granularità a livello di carattere, ogni carattere nei documenti confrontati viene analizzato per le differenze. I risultati del confronto mostreranno i cambiamenti a livello di singolo carattere, incluse aggiunte, eliminazioni e modifiche.