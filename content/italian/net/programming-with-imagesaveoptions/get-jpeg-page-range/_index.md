---
title: Ottieni intervallo di pagine Jpeg
linktitle: Ottieni intervallo di pagine Jpeg
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come ottenere una serie di pagine JPEG con Aspose.Words per .NET. Tutorial completo per l'estrazione di immagini personalizzate.
type: docs
weight: 10
url: /it/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

In questo tutorial esploreremo il codice sorgente C# fornito per la funzione "Ottieni intervallo di pagine JPEG" con Aspose.Words per .NET. Questa funzione consente di convertire un intervallo specifico di pagine di un documento in immagini in formato JPEG.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: caricamento del documento

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In questo passaggio, carichiamo il documento utilizzando il file`Document` metodo e passando il percorso del file DOCX da caricare.

## Passaggio 3: configura le opzioni di backup dell'immagine

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 In questo passaggio, configuriamo le opzioni di backup per le immagini. Ne creiamo uno nuovo`ImageSaveOptions` oggetto specificando il formato di salvataggio desiderato, qui "Jpeg" per il formato JPEG. Impostiamo anche l'intervallo di pagine da convertire utilizzando il file`PageSet`oggetto. Infine, regoliamo la luminosità e il contrasto dell'immagine utilizzando il`ImageBrightness` E`ImageContrast` proprietà, rispettivamente. Modifichiamo anche la risoluzione orizzontale utilizzando il file`HorizontalResolution` proprietà.

## Passaggio 4: backup delle immagini

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 In quest'ultimo passaggio, salviamo le immagini dell'intervallo di pagine specificato nel formato JPEG utilizzando il file`Save` metodo e passando il percorso del file di output, insieme alle opzioni di salvataggio specificate.

Ora puoi eseguire il codice sorgente per convertire un intervallo specifico di pagine nel tuo documento in immagini JPEG. Il file risultante verrà salvato nella directory specificata con il nome "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Codice sorgente di esempio per Ottieni intervallo di pagine Jpeg utilizzando Aspose.Words per .NET

```csharp 
 //Percorso della directory dei documenti
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Impostare "PageSet" su "0" per convertire solo la prima pagina di un documento.
options.PageSet = new PageSet(0);

// Modifica la luminosità e il contrasto dell'immagine.
// Entrambi sono su una scala 0-1 e sono a 0,5 per impostazione predefinita.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Modificare la risoluzione orizzontale.
// Il valore predefinito per queste proprietà è 96,0, per una risoluzione di 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità per ottenere un intervallo di pagine JPEG con Aspose.Words per .NET. Abbiamo imparato come convertire un intervallo specifico di pagine di un documento in immagini in formato JPEG, personalizzando le opzioni di salvataggio.

Questa funzione è utile quando desideri estrarre pagine specifiche da un documento e salvarle come immagini JPEG. Puoi anche regolare la luminosità, il contrasto e la risoluzione orizzontale delle immagini per ottenere risultati personalizzati.

Aspose.Words per .NET offre una vasta gamma di funzionalità avanzate per la manipolazione e la generazione di documenti. Ottenere un intervallo di pagine JPEG è uno dei tanti potenti strumenti che mette a tua disposizione.

Sentiti libero di integrare questa funzionalità nei tuoi progetti Aspose.Words per .NET per ottenere immagini JPEG di alta qualità dai tuoi documenti.