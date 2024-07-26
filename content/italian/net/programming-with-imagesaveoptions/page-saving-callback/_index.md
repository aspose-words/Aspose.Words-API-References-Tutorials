---
title: Richiamata di salvataggio della pagina
linktitle: Richiamata di salvataggio della pagina
second_title: API di elaborazione dei documenti Aspose.Words
description: Impara a salvare ogni pagina di un documento Word come immagine PNG separata utilizzando Aspose.Words per .NET con la nostra guida dettagliata passo passo.
type: docs
weight: 10
url: /it/net/programming-with-imagesaveoptions/page-saving-callback/
---
## introduzione

Ehilà! Hai mai sentito il bisogno di salvare ogni pagina di un documento Word come immagini separate? Forse vuoi suddividere un report di grandi dimensioni in immagini facilmente digeribili o forse hai bisogno di creare miniature per un'anteprima. Qualunque sia la ragione, l'utilizzo di Aspose.Words per .NET rende questo compito un gioco da ragazzi. In questa guida ti guideremo attraverso il processo di impostazione di un callback per il salvataggio della pagina per salvare ogni pagina di un documento come una singola immagine PNG. Immergiamoci subito!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Aspose.Words per .NET: se non lo hai già fatto, scaricalo e installalo da[Qui](https://releases.aspose.com/words/net/).
2. Visual Studio: qualsiasi versione dovrebbe funzionare, ma per questa guida utilizzerò Visual Studio 2019.
3. Conoscenza di base di C#: avrai bisogno di una conoscenza di base di C# per proseguire.

## Importa spazi dei nomi

Per prima cosa dobbiamo importare gli spazi dei nomi necessari. Questo ci aiuta ad accedere alle classi e ai metodi richiesti senza digitare ogni volta l'intero spazio dei nomi.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Passaggio 1: imposta la directory dei documenti

Va bene, iniziamo definendo il percorso della directory dei documenti. Qui è dove si trova il documento Word di input e dove verranno salvate le immagini di output.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il documento

Successivamente, caricheremo il documento che desideri elaborare. Assicurati che il tuo documento ("Rendering.docx") sia nella directory specificata.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: configura le opzioni di salvataggio dell'immagine

Dobbiamo configurare le opzioni per il salvataggio delle immagini. In questo caso, stiamo salvando le pagine come file PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 Qui,`PageSet` specifica l'intervallo di pagine da salvare e`PageSavingCallback` punta alla nostra classe di callback personalizzata.

## Passaggio 4: implementare la richiamata per il salvataggio della pagina

Ora implementiamo la classe di callback che gestisce il modo in cui ciascuna pagina viene salvata.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 Questa classe implementa il`IPageSavingCallback` interfaccia e all'interno di`PageSaving` metodo, definiamo il modello di denominazione per ogni pagina salvata.

## Passaggio 5: salva il documento come immagini

Infine, salviamo il documento utilizzando le opzioni configurate.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Conclusione

E il gioco è fatto! Hai impostato correttamente una richiamata di salvataggio della pagina per salvare ogni pagina di un documento Word come immagine PNG separata utilizzando Aspose.Words per .NET. Questa tecnica è incredibilmente utile per varie applicazioni, dalla creazione di anteprime di pagina alla generazione di immagini di singole pagine per i report. 

Buona programmazione!

## Domande frequenti

### Posso salvare le pagine in formati diversi da PNG?  
 Sì, puoi salvare le pagine Indiversi formati come JPEG, BMP e TIFF modificando il file`SaveFormat` in `ImageSaveOptions`.

### Cosa succede se voglio salvare solo pagine specifiche?  
 È possibile specificare le pagine che si desidera salvare regolando il file`PageSet` parametro dentro`ImageSaveOptions`.

### È possibile personalizzare la qualità dell'immagine?  
 Assolutamente! Puoi impostare proprietà come`ImageSaveOptions.JpegQuality` per controllare la qualità delle immagini in uscita.

### Come posso gestire documenti di grandi dimensioni in modo efficiente?  
Per documenti di grandi dimensioni, valuta la possibilità di elaborare le pagine in batch per gestire in modo efficace l'utilizzo della memoria.

### Dove posso trovare ulteriori informazioni su Aspose.Words per .NET?  
 Dai un'occhiata a[documentazione](https://reference.aspose.com/words/net/) per guide ed esempi completi.