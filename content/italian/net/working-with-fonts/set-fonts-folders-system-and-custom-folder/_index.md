---
title: Imposta il sistema di cartelle dei caratteri e la cartella personalizzata
linktitle: Imposta il sistema di cartelle dei caratteri e la cartella personalizzata
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare cartelle di caratteri di sistema e personalizzate nei documenti di Word utilizzando Aspose.Words per .NET, assicurando che i tuoi documenti vengano visualizzati correttamente in ambienti diversi.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## Introduzione

Immagina di creare un documento con uno stile di carattere unico, solo per scoprire che i caratteri non vengono visualizzati correttamente su un altro computer. Frustrante, vero? È qui che entra in gioco la configurazione delle cartelle dei caratteri. Con Aspose.Words per .NET, puoi definire cartelle di caratteri di sistema e personalizzate per garantire che i tuoi documenti abbiano sempre l'aspetto previsto. Vediamo come puoi raggiungere questo obiettivo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

-  Aspose.Words per .NET Library: se non l'hai già fatto, scaricalo[Qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: un IDE come Visual Studio.
- Conoscenza di base di C#: la familiarità con C# ti aiuterà a seguire gli esempi di codice.

## Importa spazi dei nomi

Innanzitutto, importa gli spazi dei nomi necessari nel tuo progetto:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Ora suddividiamo il processo in semplici passaggi.

## Passaggio 1: caricare il documento

 Per iniziare, carica il tuo documento Word in un Aspose.Words`Document` oggetto. Questo documento sarà quello in cui desideri impostare le cartelle dei caratteri.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 2: inizializza le impostazioni dei caratteri

 Crea una nuova istanza di`FontSettings`. Questo oggetto ti permetterà di gestire le fonti dei caratteri.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Passaggio 3: recuperare le origini dei caratteri di sistema

Recupera le origini dei caratteri di sistema predefinite. Su un computer Windows, questo in genere include il file "Windows\Fonts\"rubrica.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## Passaggio 4: aggiungi una cartella di caratteri personalizzata

Aggiungi una cartella personalizzata che contenga i tuoi caratteri aggiuntivi. Ciò è utile se hai font specifici non installati nella directory dei font di sistema.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## Passaggio 5: aggiorna le origini dei caratteri

 Converti nuovamente l'elenco delle origini dei caratteri in un array e impostalo su`FontSettings` oggetto.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Passaggio 6: applica le impostazioni dei caratteri al documento

 Infine, applica il configurato`FontSettings` al documento e salvarlo nel formato desiderato, ad esempio PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusione

Ed ecco qua! Seguendo questi passaggi puoi assicurarti che i tuoi documenti Word utilizzino i caratteri corretti, siano essi caratteri di sistema o personalizzati archiviati in una directory specifica. Questa configurazione aiuta a mantenere l'integrità dell'aspetto del documento in ambienti diversi.

## Domande frequenti

### Cosa succede se manca un carattere sia nella cartella di sistema che in quella personalizzata?

Aspose.Words utilizzerà un carattere predefinito per sostituire il carattere mancante, garantendo che il documento rimanga leggibile.

### Posso aggiungere più cartelle di caratteri personalizzati?

 Sì, puoi aggiungere più cartelle di caratteri personalizzati ripetendo il processo di creazione`FolderFontSource` oggetti e aggiungendoli all'elenco delle origini dei caratteri.

### È possibile utilizzare percorsi di rete per cartelle di caratteri personalizzati?

 Sì, puoi specificare un percorso di rete nel file`FolderFontSource` costruttore.

### Quali formati di file supporta Aspose.Words per il salvataggio dei documenti?

Aspose.Words supporta vari formati, inclusi DOCX, PDF, HTML e altri.

### Come gestisco le notifiche di sostituzione dei caratteri?

 È possibile gestire le notifiche di sostituzione dei caratteri utilizzando il file`FontSettings` classe`FontSubstitutionWarning`evento.