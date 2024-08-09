---
title: Ottieni l'elenco dei caratteri disponibili
linktitle: Ottieni l'elenco dei caratteri disponibili
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come ottenere un elenco di caratteri disponibili utilizzando Aspose.Words per .NET in questo tutorial dettagliato passo dopo passo. Migliora le tue capacità di gestione dei caratteri.
type: docs
weight: 10
url: /it/net/working-with-fonts/get-list-of-available-fonts/
---
## Introduzione

Ti sei mai trovato in difficoltà nel gestire i caratteri nei tuoi documenti Word? Se sei uno sviluppatore .NET, Aspose.Words per .NET è qui per salvarti! Questa potente libreria non solo ti aiuta a creare e manipolare documenti Word a livello di codice, ma offre anche ampie funzionalità di gestione dei caratteri. In questa guida ti guideremo attraverso un tutorial passo passo su come ottenere un elenco di caratteri disponibili utilizzando Aspose.Words per .NET. Lo suddivideremo in passaggi digeribili per assicurarti di poterlo seguire con facilità. Quindi, tuffiamoci e rendiamo la gestione dei caratteri un gioco da ragazzi!

## Prerequisiti

Prima di iniziare, ci sono alcune cose di cui avrai bisogno:

-  Aspose.Words per .NET: assicurati di avere la libreria Aspose.Words per .NET installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/words/net/).
- Visual Studio: questo esempio usa Visual Studio come ambiente di sviluppo.
- .NET Framework: assicurati di avere .NET Framework installato sul tuo computer.
- Directory dei documenti: un percorso di directory in cui sono archiviati i documenti.

## Importa spazi dei nomi

Innanzitutto, importa gli spazi dei nomi necessari nel tuo progetto:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## Passaggio 1: inizializza le impostazioni dei caratteri

Il primo passo è inizializzare le impostazioni del carattere. Ciò ti consentirà di gestire le fonti dei caratteri per i tuoi documenti.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings: questa classe viene utilizzata per specificare le impostazioni per la sostituzione dei caratteri e le origini dei caratteri.
- fontSources: creiamo un elenco di fonti di caratteri esistenti dalle impostazioni dei caratteri correnti.

## Passaggio 2: definire la directory dei documenti

Successivamente, specifica il percorso della directory dei documenti. Qui è dove Aspose.Words cercherà i caratteri.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: questa variabile stringa contiene il percorso della directory in cui si trovano i caratteri. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso vero e proprio.

## Passaggio 3: aggiungi la cartella dei caratteri personalizzati

Ora aggiungi una nuova sorgente di cartella per istruire Aspose.Words a cercare i caratteri in questa cartella.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: questa classe rappresenta l'origine del carattere di una cartella. Il secondo parametro (`true`) indica se cercare i caratteri in modo ricorsivo nelle sottocartelle.

## Passaggio 4: aggiorna le origini dei caratteri

Aggiungi la cartella dei caratteri personalizzati all'elenco delle origini dei caratteri esistenti e aggiorna le impostazioni dei caratteri.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource): aggiunge la cartella dei caratteri personalizzati alle origini dei caratteri esistenti.
- aggiornatoFontSources: converte l'elenco delle origini dei caratteri in un array.

## Passaggio 5: recuperare e visualizzare i caratteri

Infine, recupera i caratteri disponibili e visualizza i loro dettagli.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): recupera l'elenco dei caratteri disponibili dalla prima origine dei caratteri nell'elenco aggiornato.
-  fontInfo: un'istanza di`PhysicalFontInfo` contenente dettagli su ciascun carattere.

## Conclusione

Congratulazioni! Hai recuperato con successo un elenco di caratteri disponibili utilizzando Aspose.Words per .NET. Questo tutorial ti ha guidato attraverso ogni passaggio, dall'inizializzazione delle impostazioni dei caratteri alla visualizzazione dei dettagli dei caratteri. Con questa conoscenza, ora puoi gestire facilmente i caratteri nei tuoi documenti Word. Ricorda, Aspose.Words per .NET è un potente strumento che può migliorare significativamente le tue capacità di elaborazione dei documenti. Quindi, vai avanti ed esplora più funzionalità per rendere il tuo processo di sviluppo ancora più efficiente.

## Domande frequenti

### Posso utilizzare Aspose.Words per .NET con altri framework .NET?
Sì, Aspose.Words per .NET è compatibile con vari framework .NET tra cui .NET Core e .NET 5+.

### Come installo Aspose.Words per .NET?
È possibile installarlo tramite NuGet Package Manager in Visual Studio cercando "Aspose.Words".

### È possibile aggiungere più cartelle di caratteri personalizzati?
 Sì, puoi aggiungere più cartelle di caratteri personalizzati creandone più`FolderFontSource` istanze e aggiungendole all'elenco delle origini dei caratteri.

### Posso recuperare i dettagli del carattere da una fonte di carattere specifica?
 Sì, puoi recuperare i dettagli del carattere da qualsiasi fonte di carattere specificando l'indice della fonte di carattere nel file`updatedFontSources` vettore.

### Aspose.Words per .NET supporta la sostituzione dei caratteri?
Sì, supporta la sostituzione dei caratteri per garantire che il testo venga visualizzato correttamente anche se il carattere originale non è disponibile.