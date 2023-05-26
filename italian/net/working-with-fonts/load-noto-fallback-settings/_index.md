---
title: Carica le impostazioni di fallback Noto
linktitle: Carica le impostazioni di fallback Noto
second_title: Riferimento all'API Aspose.Words per .NET
description: In questo tutorial, scopri come caricare i parametri di override Noto in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/load-noto-fallback-settings/
---
In questo tutorial, ti illustreremo come caricare le impostazioni di sostituzione dei caratteri Noto in un documento Word utilizzando Aspose.Words Library per .NET. Le impostazioni di Noto Font Substitution consentono di gestire la sostituzione dei font durante la visualizzazione o la stampa dei documenti. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto

## Passaggio 1: definire la directory dei documenti
 Innanzitutto, devi impostare il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento e configurare le impostazioni di sostituzione dei caratteri
 Successivamente, caricheremo il documento utilizzando il file`Document` class e configurare le impostazioni di sovrascrittura dei caratteri utilizzando il file`FontSettings` classe. Caricheremo le impostazioni di fallback del font Noto usando il file`LoadNotoFallbackSettings()` metodo.

```csharp
// Carica il documento e configura le impostazioni di sostituzione dei caratteri
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
```

## Passaggio 3: salvare il documento
Infine, salveremo il documento con le impostazioni di sostituzione del carattere Noto applicate.

```csharp
// Salva il documento
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");
```


### Esempio di codice sorgente per Noto Fallback Settings utilizzando Aspose.Words per .NET 
```csharp

// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");

```

## Conclusione
In questo tutorial, abbiamo visto come caricare le impostazioni di sostituzione dei caratteri Noto in un documento Word con Aspose.Words per .NET. Le impostazioni di sostituzione dei caratteri di Noto ti consentono di gestire la sostituzione dei caratteri per migliorare la visualizzazione e la stampa dei tuoi documenti. Sentiti libero di utilizzare questa funzione per personalizzare la sostituzione dei caratteri in base alle tue esigenze.