---
title: Abilita Disabilita sostituzione carattere
linktitle: Abilita Disabilita sostituzione carattere
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come abilitare o disabilitare la sostituzione dei caratteri nei documenti di Word utilizzando Aspose.Words per .NET. Assicurati che i tuoi documenti appaiano coerenti su tutte le piattaforme.
type: docs
weight: 10
url: /it/net/working-with-fonts/enable-disable-font-substitution/
---
## Introduzione

Ti sei mai trovato in una situazione in cui i caratteri scelti meticolosamente in un documento Word vengono sostituiti quando vengono visualizzati su un altro computer? Fastidioso, vero? Ciò accade a causa della sostituzione dei caratteri, un processo in cui il sistema sostituisce un carattere mancante con uno disponibile. Ma non preoccuparti! Con Aspose.Words per .NET, puoi gestire e controllare facilmente la sostituzione dei caratteri. In questo tutorial ti guideremo attraverso i passaggi per abilitare o disabilitare la sostituzione dei caratteri nei tuoi documenti Word, assicurandoti che i tuoi documenti abbiano sempre l'aspetto che desideri.

## Prerequisiti

Prima di addentrarci nei passaggi, assicuriamoci di avere tutto ciò di cui hai bisogno:

-  Aspose.Words per .NET: scarica la versione più recente[Qui](https://releases.aspose.com/words/net/).
- Visual Studio: qualsiasi versione che supporti .NET.
- Conoscenza di base di C#: questo ti aiuterà a seguire gli esempi di codifica.

## Importa spazi dei nomi

Per iniziare, assicurati di aver importato gli spazi dei nomi necessari nel tuo progetto. Aggiungi questi nella parte superiore del tuo file C#:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Ora suddividiamo il processo in passaggi semplici e gestibili.

## Passaggio 1: imposta il tuo progetto

Innanzitutto, imposta un nuovo progetto in Visual Studio e aggiungi un riferimento alla libreria Aspose.Words per .NET. Se non l'hai già fatto, scaricalo da[Sito web Aspose](https://releases.aspose.com/words/net/).

## Passaggio 2: carica il documento

Successivamente, carica il documento con cui vuoi lavorare. Ecco come farlo:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti. Questo codice carica il documento in memoria in modo da poterlo manipolare.

## Passaggio 3: configura le impostazioni dei caratteri

 Ora creiamo un file`FontSettings` oggetto per gestire le impostazioni di sostituzione dei caratteri:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Passaggio 4: imposta la sostituzione del carattere predefinito

Imposta la sostituzione del carattere predefinito con un carattere di tua scelta. Questo carattere verrà utilizzato se il carattere originale non è disponibile:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

In questo esempio, utilizziamo Arial come carattere predefinito.

## Passaggio 5: disabilita la sostituzione delle informazioni sui caratteri

Per disabilitare la sostituzione delle informazioni sui caratteri, che impedisce al sistema di sostituire i caratteri mancanti con quelli disponibili, utilizzare il seguente codice:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Passaggio 6: applicare le impostazioni dei caratteri al documento

Ora applica queste impostazioni al tuo documento:

```csharp
doc.FontSettings = fontSettings;
```

## Passaggio 7: salva il documento

Infine, salva il documento modificato. Puoi salvarlo nel formato che preferisci. Per questo tutorial, lo salveremo come PDF:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Conclusione

Ed ecco qua! Seguendo questi passaggi, puoi facilmente controllare la sostituzione dei caratteri nei tuoi documenti Word utilizzando Aspose.Words per .NET. Ciò garantisce che i tuoi documenti mantengano l'aspetto previsto, indipendentemente da dove vengono visualizzati.

## Domande frequenti

### Posso utilizzare caratteri diversi da Arial per la sostituzione?

 Assolutamente! Puoi specificare qualsiasi carattere disponibile sul tuo sistema modificando il nome del carattere nel file`DefaultFontName` proprietà.

### Cosa succede se il carattere predefinito specificato non è disponibile?

Se il carattere predefinito non è disponibile, Aspose.Words utilizzerà un meccanismo di fallback del sistema per trovare un sostituto appropriato.

### Posso abilitare nuovamente la sostituzione dei caratteri dopo averla disabilitata?

 Sì, puoi attivare/disattivare il file`Enabled` proprietà di`FontInfoSubstitution` tornare a`true` se desideri abilitare nuovamente la sostituzione dei caratteri.

### C'è un modo per verificare quali caratteri vengono sostituiti?

Sì, Aspose.Words fornisce metodi per registrare e tenere traccia della sostituzione dei caratteri, consentendoti di vedere quali caratteri vengono sostituiti.

### Posso utilizzare questo metodo per altri formati di documenti oltre a DOCX?

Decisamente! Aspose.Words supporta vari formati e puoi applicare queste impostazioni dei caratteri a qualsiasi formato supportato.