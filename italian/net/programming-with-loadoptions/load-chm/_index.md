---
title: Carica Chm
linktitle: Carica Chm
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come caricare i file CHM con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-loadoptions/load-chm/
---

Quando si lavora con i file della Guida HTML (CHM) in un'applicazione C#, è importante poterli caricare correttamente. Con la libreria Aspose.Words per .NET, puoi caricare facilmente i file CHM utilizzando le opzioni di caricamento appropriate. In questa guida dettagliata, ti mostreremo come utilizzare Aspose.Words per il codice sorgente .NET C# per caricare un file CHM utilizzando le opzioni di caricamento LoadOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Configurazione delle opzioni di caricamento

Il primo passo è configurare le opzioni di caricamento per il nostro file CHM. Utilizzare la classe LoadOptions per specificare i parametri di caricamento. Nel nostro caso, dobbiamo impostare la proprietà Encoding sulla codifica appropriata per i file CHM, in genere "windows-1251". Ecco come farlo:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

Creiamo un nuovo oggetto LoadOptions e impostiamo la proprietà Encoding sulla codifica "windows-1251" per i file CHM.

## Caricamento del file CHM

Ora che abbiamo configurato le opzioni di caricamento, possiamo caricare il file CHM utilizzando la classe Document e specificare le opzioni di caricamento. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

In questo esempio, carichiamo il file CHM "HTML help.chm" situato nella directory dei documenti utilizzando le opzioni di caricamento specificate.

### Codice sorgente di esempio per LoadOptions con funzionalità "Load Chm" utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configurazione delle opzioni di caricamento con la funzione "Load Chm".
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

// Carica il file CHM con le opzioni specificate
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## Conclusione

In questa guida, abbiamo spiegato come caricare un file CHM utilizzando la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e usando il codice sorgente C# fornito, puoi facilmente applicare questa funzionalità nella tua applicazione C#. Caricare correttamente i file CHM è essenziale per poterli manipolare e convertire in modo efficiente con Aspose.Words.