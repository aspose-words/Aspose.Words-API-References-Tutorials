---
title: Formato 1Bpp indicizzato
linktitle: Formato 1Bpp indicizzato
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come formattare le immagini in 1 bpp indicizzate con Aspose.Words per .NET. Tutorial completo per immagini a bassa profondità di colore.
type: docs
weight: 10
url: /it/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
In questo tutorial, esploreremo il codice sorgente C# fornito per la funzionalità "Formato 1Bpp indicizzato" con Aspose.Words per .NET. Questa funzione consente di formattare le immagini in un documento in formato PNG con una profondità di colore di 1 bit per pixel (1 bpp) e una modalità colore indicizzata.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: caricamento del documento

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In questo passaggio, carichiamo il documento utilizzando il file`Document` metodo e passando il percorso al file DOCX da caricare.

## Passaggio 3: configurare le opzioni di backup dell'immagine

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 In questo passaggio, configuriamo le opzioni di backup per le immagini. Creiamo un nuovo`ImageSaveOptions`oggetto specificando il formato di salvataggio desiderato, qui "Png" per il formato PNG. Definiamo anche la pagina da includere nell'immagine, la modalità colore bianco e nero e il formato pixel 1 bpp indicizzato.

## Passaggio 4: backup delle immagini

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 In quest'ultimo passaggio, salviamo le immagini del documento nel formato PNG utilizzando il file`Save` metodo e passando il percorso al file di output, insieme alle opzioni di salvataggio specificate.

Ora puoi eseguire il codice sorgente per formattare le immagini del documento nel formato PNG con una profondità di colore di 1 bpp indicizzato. Il file risultante verrà salvato nella directory specificata con il nome "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Esempio di codice sorgente per il formato 1Bpp indicizzato utilizzando Aspose.Words per .NET

```csharp 
 
			 //Percorso della directory dei documenti
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Conclusione

In questo tutorial, abbiamo esplorato la funzionalità del formato indicizzato 1Bpp con Aspose.Words per .NET. Abbiamo imparato come formattare le immagini in un documento in formato PNG con una profondità di colore di 1 bit per pixel (1 bpp) e una modalità colore indicizzata.

Questa funzione è utile quando si desidera ottenere immagini con bassa profondità di colore e file di piccole dimensioni. Il formato 1Bpp Indexed consente di rappresentare le immagini utilizzando una tavolozza di colori indicizzata, che può essere vantaggiosa per alcune applicazioni specifiche.

Aspose.Words per .NET offre una vasta gamma di funzionalità avanzate per la manipolazione e la generazione di documenti. Il formato 1Bpp Indexed è uno dei tanti potenti strumenti che mette a tua disposizione.