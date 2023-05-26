---
title: Impostazioni carattere Istanza predefinita
linktitle: Impostazioni carattere Istanza predefinita
second_title: Riferimento all'API Aspose.Words per .NET
description: In questo tutorial, scopri come configurare le impostazioni predefinite dei caratteri in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/font-settings-default-instance/
---

In questo tutorial, ti illustreremo come configurare le impostazioni predefinite dei caratteri in un documento Word utilizzando la libreria Aspose.Words per .NET. Le impostazioni predefinite dei caratteri consentono di specificare le origini dei caratteri utilizzate durante il caricamento e il rendering dei documenti. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

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

## Passaggio 2: configurare le impostazioni dei caratteri predefiniti
 Successivamente, creeremo un'istanza di`FontSettings` utilizzando`FontSettings.DefaultInstance`quindi specificheremo le origini dei caratteri utilizzate durante il caricamento e il rendering dei documenti. In questo esempio, stiamo usando un'origine font di sistema e un'origine font cartella.

```csharp
// Configura le impostazioni dei caratteri predefiniti
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Passaggio 3: carica il documento con le impostazioni dei caratteri
 Ora caricheremo il documento usando`LoadOptions` e specificando le impostazioni dei caratteri da utilizzare.

```csharp
// Carica il documento con le impostazioni del carattere
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Codice sorgente di esempio per l'istanza predefinita delle impostazioni dei caratteri utilizzando Aspose.Words per .NET 
```csharp

// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusione
In questo tutorial, abbiamo visto come configurare le impostazioni predefinite dei caratteri in un documento Word con Aspose.Words per .NET. Specificando le origini dei caratteri utilizzate durante il caricamento e il rendering dei documenti, è possibile controllare l'aspetto dei caratteri nei documenti. Sentiti libero di utilizzare questa funzione per personalizzare le impostazioni dei caratteri nei tuoi progetti.