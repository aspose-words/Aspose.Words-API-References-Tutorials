---
title: Imposta le impostazioni di fallback dei caratteri
linktitle: Imposta le impostazioni di fallback dei caratteri
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come configurare le impostazioni di sostituzione dei caratteri in Aspose.Words per .NET e personalizzare la sostituzione dei caratteri nei documenti di Word.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-font-fallback-settings/
---
In questo tutorial, ti mostreremo come impostare le impostazioni di sostituzione dei caratteri in un documento di Word usando Aspose.Words per .NET. Le impostazioni di sostituzione dei caratteri consentono di specificare i caratteri sostitutivi da utilizzare quando i caratteri specificati non sono disponibili.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto

## Passaggio 1: definire la directory dei documenti
Inizia impostando il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: carica le impostazioni di sostituzione dei caratteri
 Crea un'istanza di`FontSettings` classe e utilizzare il`Load`metodo per caricare le impostazioni di sostituzione dei caratteri da un file XML. Il file XML specificato deve contenere le regole di sostituzione dei caratteri da utilizzare.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Passaggio 3: applica le impostazioni di sostituzione dei caratteri
 Associa le impostazioni di sostituzione dei caratteri al documento assegnandole a quelle del documento`FontSettings` proprietà.

```csharp
doc.FontSettings = fontSettings;
```

## Passaggio 4: salvare il documento
 Salvare il documento utilizzando il file`Save` metodo del`Document` con il percorso e il nome file appropriati.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Esempio di codice sorgente per Set Font Fallback Settings utilizzando Aspose.Words per .NET 
```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Conclusione
In questo tutorial, hai imparato come impostare le impostazioni di sostituzione dei caratteri in un documento di Word utilizzando Aspose.Words per .NET. Sperimenta con diverse regole di sostituzione dei caratteri per assicurarti che il tuo documento appaia coerente, anche quando i caratteri specificati non sono disponibili.
