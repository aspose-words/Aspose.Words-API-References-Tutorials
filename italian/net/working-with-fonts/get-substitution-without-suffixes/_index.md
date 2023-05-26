---
title: Ottieni sostituzione senza suffissi
linktitle: Ottieni sostituzione senza suffissi
second_title: Riferimento all'API Aspose.Words per .NET
description: In questo tutorial, scopri come ottenere sostituzioni senza suffisso in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/get-substitution-without-suffixes/
---

In questo tutorial, ti mostreremo come ottenere le sostituzioni senza suffissi in un documento Word utilizzando la libreria Aspose.Words per .NET. Le sostituzioni senza suffissi vengono utilizzate per risolvere i problemi di sostituzione dei caratteri durante la visualizzazione o la stampa di documenti. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

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

## Passaggio 2: caricare il documento e configurare le sostituzioni senza suffissi
 Successivamente, caricheremo il documento utilizzando il file`Document` class e configurare le sostituzioni senza suffisso utilizzando il file`DocumentSubstitutionWarnings` classe. Aggiungeremo anche una fonte di carattere specificando una cartella contenente i caratteri.

```csharp
//Carica il documento e configura le sostituzioni senza suffissi
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Passaggio 3: salvare il documento
Infine, salveremo il documento con le sostituzioni senza suffisso applicate.

```csharp
// Salva il documento
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Esempio di codice sorgente per Ottieni sostituzione senza suffissi utilizzando Aspose.Words per .NET 
```csharp

// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Conclusione
In questo tutorial abbiamo visto come ottenere le sostituzioni senza suffissi in un documento Word con Aspose.Words per .NET. Le sostituzioni senza suffissi sono utili per risolvere i problemi di sostituzione dei caratteri. Sentiti libero di utilizzare questa funzione per migliorare la visualizzazione e la stampa dei tuoi documenti.
