---
title: Risorsa Fonte di font Steam Esempio
linktitle: Risorsa Fonte di font Steam Esempio
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare Resource Stream Font Source per caricare font personalizzati in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/resource-steam-font-source-example/
---

In questo tutorial, ti illustreremo come utilizzare Resource Flow Font Source con Aspose.Words per .NET. Questa fonte di font ti consente di caricare font da un flusso di risorse, che può essere utile quando vuoi incorporare font personalizzati nella tua applicazione.

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

## Passaggio 2: caricare il documento e impostare l'origine del carattere del flusso di risorse
 Successivamente, caricheremo il documento utilizzando il file`Document` class e impostare l'origine del font del flusso di risorse utilizzando il file`FontSettings.DefaultInstance.SetFontsSources()` classe. Ciò consentirà ad Aspose.Words di trovare i caratteri nel flusso di risorse.

```csharp
// Carica il documento e imposta l'origine del font del flusso di risorse
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## Passaggio 3: salvare il documento
Infine, salveremo il documento. I caratteri verranno caricati dal flusso di risorse specificato e incorporati nel documento.

```csharp
// Salva il documento
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Esempio di codice sorgente per Resource Steam Font Source Esempio con Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Conclusione
In questo tutorial, hai imparato come utilizzare Resource Flow Font Source con Aspose.Words per .NET. Questa funzione ti consente di caricare i caratteri da un feed di risorse, utile quando desideri incorporare caratteri personalizzati nei tuoi documenti. Sperimenta con diversi font ed esplora le possibilità offerte da Aspose.Words per la gestione dei font.
