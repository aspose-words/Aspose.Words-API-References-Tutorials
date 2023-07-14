---
title: Obiettivo di confronto
linktitle: Obiettivo di confronto
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri la funzionalità di confronto target di Aspose.Words per .NET che ti consente di confrontare documenti e generare un nuovo documento contenente le modifiche apportate.
type: docs
weight: 10
url: /it/net/compare-documents/comparison-target/
---

Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità di destinazione del confronto di Aspose.Words per .NET.

## Passaggio 1: Introduzione

La funzione di confronto di destinazione di Aspose.Words per .NET consente di confrontare due documenti e generare un nuovo documento contenente le modifiche apportate al documento di destinazione. Questo può essere utile per tenere traccia delle modifiche apportate tra le diverse versioni di un documento.

## Passaggio 2: configurazione dell'ambiente

Prima di iniziare, devi configurare il tuo ambiente di sviluppo per lavorare con Aspose.Words per .NET. Assicurati di aver installato la libreria Aspose.Words e di avere un progetto C# adatto in cui incorporare il codice.

## Passaggio 3: aggiungere gli assembly richiesti

Per utilizzare la funzione di destinazione del confronto di Aspose.Words per .NET, è necessario aggiungere gli assembly necessari al progetto. Assicurati di avere i riferimenti corretti ad Aspose.Words nel tuo progetto.

```csharp
using Aspose.Words;
```

## Passaggio 4: inizializzazione del documento

In questo passaggio, inizializzeremo due documenti per il confronto. È necessario specificare il percorso della directory in cui si trovano i documenti, nonché il nome del documento di origine.

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inizializzazione del documento A da confrontare.
Document docA = new Document(dataDir + "DocumentA.docx");

// Clona il documento A per creare una copia identica del documento B.
Document docB = docA.Clone();
```

## Passaggio 5: configurazione delle opzioni di confronto

In questo passaggio, configureremo le opzioni di confronto per specificare il comportamento del confronto. Le opzioni includono la possibilità di ignorare la formattazione, nonché l'obiettivo di confronto, ovvero l'opzione "Mostra modifiche in" nella finestra di dialogo "Confronta documenti" di Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Passaggio 6: confronto dei documenti

Ora confronteremo i documenti e genereremo il risultato in un nuovo documento.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 IL`Compare` Il metodo confronta il documento A con il documento B e salva le modifiche al documento A. È possibile specificare il nome utente e la data del confronto come riferimento.

### Esempio di codice sorgente per Comparison Target utilizzando Aspose.Words per .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Si riferisce all'opzione "Mostra modifiche in" di Microsoft Word nella finestra di dialogo "Confronta documenti".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Conclusione

In questo articolo, abbiamo esplorato la funzionalità di destinazione diff di Aspose.Words per .NET. Questa funzionalità consente di confrontare due documenti e generare un nuovo documento contenente le modifiche apportate. Puoi utilizzare questa conoscenza per tenere traccia delle modifiche tra le diverse versioni dei tuoi documenti.

