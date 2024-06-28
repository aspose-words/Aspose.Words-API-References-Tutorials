---
title: Configura le impostazioni di fallback dei caratteri
linktitle: Configura le impostazioni di fallback dei caratteri
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come configurare le impostazioni di fallback dei caratteri in Aspose.Words per .NET. Questa guida completa garantisce che tutti i caratteri nei tuoi documenti vengano visualizzati correttamente.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-font-fallback-settings/
---

Quando si lavora con documenti che contengono diversi elementi di testo, come lingue diverse o caratteri speciali, è fondamentale garantire che questi elementi vengano visualizzati correttamente. Aspose.Words per .NET offre una potente funzionalità chiamata Impostazioni di fallback dei caratteri, che aiuta a definire le regole per la sostituzione dei caratteri quando il carattere originale non supporta determinati caratteri. In questa guida, esploreremo come configurare le impostazioni di fallback dei caratteri utilizzando Aspose.Words per .NET in un tutorial passo passo.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

- Conoscenza di base di C#: familiarità con il linguaggio di programmazione C# e il framework .NET.
-  Aspose.Words per .NET: scarica e installa da[Link per scaricare](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: una configurazione come Visual Studio per scrivere ed eseguire il codice.
-  Documento di esempio: disporre di un documento di esempio (ad es.`Rendering.docx`) pronto per il test.
- XML delle regole di fallback dei caratteri: preparare un file XML che definisce le regole di fallback dei caratteri.

## Importa spazi dei nomi

Per utilizzare Aspose.Words, è necessario importare gli spazi dei nomi necessari. Ciò consente l'accesso a varie classi e metodi richiesti per l'elaborazione dei documenti.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Passaggio 1: definire la directory dei documenti

Innanzitutto, definisci la directory in cui è archiviato il tuo documento. Questo è essenziale per individuare ed elaborare il documento.

```csharp
// Il percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento

 Carica il tuo documento in un Aspose.Words`Document` oggetto. Questo passaggio consente di lavorare con il documento a livello di codice.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: configura le impostazioni dei caratteri

 Creane uno nuovo`FontSettings` oggetto e caricare le impostazioni di fallback dei caratteri da un file XML. Questo file XML contiene le regole per il fallback dei caratteri.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Passaggio 4: applica le impostazioni dei caratteri al documento

 Assegnare il configurato`FontSettings`al documento. Ciò garantisce che le regole di fallback dei caratteri vengano applicate durante il rendering del documento.

```csharp
doc.FontSettings = fontSettings;
```

## Passaggio 5: salva il documento

Infine, salva il documento. Le impostazioni di fallback dei caratteri verranno utilizzate durante l'operazione di salvataggio per garantire la corretta sostituzione dei caratteri.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## File XML: regole di fallback dei caratteri

Ecco un esempio di come dovrebbe apparire il tuo file XML che definisce le regole di fallback dei caratteri:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Conclusione

Seguendo questi passaggi, è possibile configurare e utilizzare in modo efficace le impostazioni di fallback dei caratteri in Aspose.Words per .NET. Ciò garantisce che i tuoi documenti visualizzino correttamente tutti i caratteri, anche se il carattere originale non supporta determinati caratteri. L'implementazione di queste impostazioni migliorerà notevolmente la qualità e la leggibilità dei tuoi documenti.

## Domande frequenti

### Q1: Cos'è il fallback dei caratteri?

Font Fallback è una funzionalità che consente la sostituzione dei caratteri quando il carattere originale non supporta determinati caratteri, garantendo la corretta visualizzazione di tutti gli elementi di testo.

### Q2: Posso specificare più caratteri di fallback?

Sì, puoi specificare più caratteri di fallback nelle regole XML. Aspose.Words controllerà ciascun carattere nell'ordine specificato finché non ne troverà uno che supporti il carattere.

### Q3: Dove posso scaricare Aspose.Words per .NET?

 Puoi scaricarlo da[Asporre la pagina di download](https://releases.aspose.com/words/net/).

### Q4: Come posso creare il file XML per le regole di fallback dei caratteri?

Il file XML può essere creato utilizzando qualsiasi editor di testo. Dovrebbe seguire la struttura mostrata nell'esempio fornito in questo tutorial.

### Q5: è disponibile il supporto per Aspose.Words?

 Sì, puoi trovare supporto su[Forum di supporto di Aspose.Words](https://forum.aspose.com/c/words/8).