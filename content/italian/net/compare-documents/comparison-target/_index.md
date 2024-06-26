---
title: Obiettivo di confronto nel documento di Word
linktitle: Obiettivo di confronto nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Impara a confrontare l'obiettivo nella funzionalità del documento word di Aspose.Words per .NET che ti consente di confrontare documenti e generare un nuovo documento contenente le modifiche apportate.
type: docs
weight: 10
url: /it/net/compare-documents/comparison-target/
---
Ecco una guida passo passo per spiegare il codice sorgente C# di seguito, che utilizza l'obiettivo di confronto nella funzionalità del documento Word di Aspose.Words per .NET.

## Passaggio 1: introduzione

La funzionalità di confronto di destinazione di Aspose.Words per .NET consente di confrontare due documenti e generare un nuovo documento contenente le modifiche apportate al documento di destinazione. Ciò può essere utile per tenere traccia delle modifiche apportate tra diverse versioni di un documento.

## Passaggio 2: configurazione dell'ambiente

Prima di iniziare, devi configurare il tuo ambiente di sviluppo per lavorare con Aspose.Words per .NET. Assicurati di avere la libreria Aspose.Words installata e di avere un progetto C# adatto in cui incorporare il codice.

## Passaggio 3: aggiungere gli assiemi richiesti

Per utilizzare la funzionalità di destinazione del confronto di Aspose.Words per .NET, è necessario aggiungere gli assembly necessari al progetto. Assicurati di avere i riferimenti corretti ad Aspose.Words nel tuo progetto.

```csharp
using Aspose.Words;
```

## Passaggio 4: inizializzazione del documento

In questo passaggio inizializzeremo due documenti per il confronto. È necessario specificare il percorso della directory in cui si trovano i documenti, nonché il nome del documento di origine.

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inizializzazione del documento A da confrontare.
Document docA = new Document(dataDir + "DocumentA.docx");

// Clona il documento A per creare una copia identica del documento B.
Document docB = docA.Clone();
```

## Passaggio 5: configurazione delle opzioni di confronto

In questo passaggio, configureremo le opzioni di confronto per specificare il comportamento del confronto. Le opzioni includono la possibilità di ignorare la formattazione, nonché l'obiettivo del confronto, ovvero l'opzione "Mostra modifiche in" nella finestra di dialogo "Confronta documenti" di Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Passaggio 6: confronto dei documenti

Ora confronteremo i documenti e genereremo il risultato in un nuovo documento.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 IL`Compare`confronta il documento A con il documento B e salva le modifiche nel documento A. È possibile specificare il nome utente e la data del confronto come riferimento.

### Codice sorgente di esempio per Confronta destinazione utilizzando Aspose.Words per .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Si riferisce all'opzione "Mostra modifiche in" di Microsoft Word nella finestra di dialogo "Confronta documenti".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Conclusione

In questo articolo, abbiamo esplorato la funzionalità di destinazione diff di Aspose.Words per .NET. Questa funzionalità consente di confrontare due documenti e generare un nuovo documento contenente le modifiche apportate. Puoi utilizzare questa conoscenza per tenere traccia delle modifiche tra le diverse versioni dei tuoi documenti.

### Domande frequenti

#### D: Qual è lo scopo dell'utilizzo di Comparison Target in Aspose.Words per .NET?

R: Il confronto target in Aspose.Words per .NET consente di confrontare due documenti e generare un nuovo documento contenente le modifiche apportate al documento di destinazione. Questa funzionalità è utile per tenere traccia delle modifiche apportate tra diverse versioni di un documento e visualizzare le differenze in un documento separato.

#### D: Come posso utilizzare Comparison Target in Aspose.Words per .NET?

R: Per utilizzare Comparison Target in Aspose.Words per .NET, attenersi alla seguente procedura:
1. Configura il tuo ambiente di sviluppo con la libreria Aspose.Words.
2. Aggiungi gli assembly necessari al tuo progetto facendo riferimento ad Aspose.Words.
3.  Inizializza i documenti che desideri confrontare utilizzando il file`Document` classe o il`DocumentBuilder` classe.
4.  Configura le opzioni di confronto creando un file`CompareOptions` oggetto e impostazione di proprietà come`IgnoreFormatting` E`Target` (per esempio.,`ComparisonTargetType.New` per obiettivo di confronto).
5.  Usa il`Compare` metodo su un documento, passando l'altro documento e il`CompareOptions` oggetto come parametri. Questo metodo confronterà i documenti e salverà le modifiche nel primo documento.

####  D: Qual è lo scopo di`Target` property in the `CompareOptions` class?

 R: Il`Target` proprietà nel`CompareOptions` class consente di specificare l'obiettivo del confronto, che è simile all'opzione "Mostra modifiche in" nella finestra di dialogo "Confronta documenti" di Microsoft Word. L'obiettivo può essere impostato su`ComparisonTargetType.New` per mostrare le modifiche in un nuovo documento,`ComparisonTargetType.Current` per mostrare le modifiche nel documento corrente, oppure`ComparisonTargetType.Formatting` per mostrare solo le modifiche alla formattazione.