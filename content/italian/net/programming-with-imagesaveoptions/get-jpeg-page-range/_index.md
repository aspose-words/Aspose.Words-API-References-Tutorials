---
title: Ottieni intervallo di pagine Jpeg
linktitle: Ottieni intervallo di pagine Jpeg
second_title: API di elaborazione dei documenti Aspose.Words
description: Converti pagine specifiche di documenti Word in JPEG con impostazioni personalizzate utilizzando Aspose.Words per .NET. Scopri come regolare la luminosità, il contrasto e la risoluzione passo dopo passo.
type: docs
weight: 10
url: /it/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---
## Introduzione

La conversione di documenti Word in immagini può essere incredibilmente utile, sia che tu stia creando miniature, visualizzando l'anteprima di documenti online o condividendo contenuti in un formato più accessibile. Con Aspose.Words per .NET, puoi convertire facilmente pagine specifiche dei tuoi documenti Word in formato JPEG personalizzando varie impostazioni come luminosità, contrasto e risoluzione. Vediamo come raggiungere questo obiettivo passo dopo passo!

## Prerequisiti

Prima di iniziare, avrai bisogno di alcune cose:

-  Aspose.Words per .NET: assicurati di avere Aspose.Words per .NET installato. Puoi[scaricalo qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: ambiente di sviluppo AC# come Visual Studio.
- Documento di esempio: un documento Word con cui lavorare. Per questo tutorial è possibile utilizzare qualsiasi file .docx.
- Conoscenza di base del C#: familiarità con la programmazione C#.

Una volta che li hai pronti, iniziamo!

## Importa spazi dei nomi

Per utilizzare Aspose.Words per .NET, dovrai importare gli spazi dei nomi necessari all'inizio del codice. Ciò garantisce l'accesso a tutte le classi e i metodi richiesti per la manipolazione dei documenti.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Passaggio 1: carica il documento

Per prima cosa dobbiamo caricare il documento Word che vogliamo convertire. Supponiamo che il nostro documento abbia un nome`Rendering.docx` e si trova nella directory specificata dal segnaposto`YOUR DOCUMENT DIRECTORY`.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Questo codice inizializza il percorso del documento e lo carica in un Aspose.Words`Document` oggetto.

## Passaggio 2: imposta ImageSaveOptions

 Successivamente, configureremo il file`ImageSaveOptions` per specificare come vogliamo che venga generato il nostro JPEG. Ciò include l'impostazione dell'intervallo di pagine, della luminosità dell'immagine, del contrasto e della risoluzione.

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options.PageSet = new PageSet(0); // Converti solo la prima pagina
options.ImageBrightness = 0.3f;   // Imposta la luminosità
options.ImageContrast = 0.7f;     // Imposta il contrasto
options.HorizontalResolution = 72f; // Imposta la risoluzione
```

## Passaggio 3: salva il documento come JPEG

Infine, salviamo il documento come file JPEG utilizzando le impostazioni che abbiamo definito.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Questo codice salva la prima pagina di`Rendering.docx` come immagine JPEG con le impostazioni di luminosità, contrasto e risoluzione specificate.

## Conclusione

Ed ecco qua! Hai convertito con successo una pagina specifica di un documento Word in un'immagine JPEG con impostazioni personalizzate utilizzando Aspose.Words per .NET. Questo processo può essere personalizzato per soddisfare varie esigenze, sia che tu stia preparando immagini per un sito Web, creando anteprime di documenti o altro.

## Domande frequenti

### Posso convertire più pagine contemporaneamente?
 Sì, puoi specificare un intervallo di pagine utilizzando il file`PageSet` proprietà dentro`ImageSaveOptions`.

### Come posso regolare la qualità dell'immagine?
 È possibile regolare la qualità del JPEG utilizzando il comando`JpegQuality` proprietà dentro`ImageSaveOptions`.

### Posso salvare in altri formati di immagine?
 Sì, Aspose.Words supporta vari formati di immagine come PNG, BMP e TIFF. Cambia il`SaveFormat` In`ImageSaveOptions` di conseguenza.

### C'è un modo per visualizzare l'anteprima dell'immagine prima di salvarla?
Dovresti implementare un meccanismo di anteprima separatamente, poiché Aspose.Words non fornisce una funzionalità di anteprima incorporata.

### Come posso ottenere una licenza temporanea per Aspose.Words?
 Puoi richiedere un[licenza temporanea qui](https://purchase.aspose.com/temporary-license/).