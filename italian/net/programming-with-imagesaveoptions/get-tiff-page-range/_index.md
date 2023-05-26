---
title: Ottieni l'intervallo di pagine Tiff
linktitle: Ottieni l'intervallo di pagine Tiff
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come estrarre una serie di pagine TIFF con Aspose.Words per .NET. Tutorial completo per file TIFF personalizzati.
type: docs
weight: 10
url: /it/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

In questo tutorial, esploreremo il codice sorgente C# fornito per ottenere una gamma di pagine TIFF con Aspose.Words per .NET. Questa funzione consente di estrarre un intervallo specifico di pagine da un documento e salvarle come file TIFF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: caricamento del documento

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 In questo passaggio, carichiamo il documento utilizzando il file`Document` metodo e passando il percorso al file DOCX da caricare.

## Passaggio 3: salvare il documento completo in TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 In questo passaggio, salviamo il documento completo in formato TIFF utilizzando il file`Save` metodo e specificando il percorso del file di output con l'estensione`.tiff`.

## Passaggio 4: configurare le opzioni di backup per l'intervallo di pagine

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 In questo passaggio, configuriamo le opzioni di backup per l'intervallo di pagine specifico. Creiamo un nuovo`ImageSaveOptions` oggetto specificando il formato di salvataggio desiderato, qui "Tiff" per il formato TIFF. Noi usiamo`PageSet` per specificare l'intervallo di pagine che vogliamo estrarre, qui dalla pagina 0 alla pagina 1 (incluse). Impostiamo anche la compressione TIFF su`Ccitt4` e la risoluzione a 160 dpi.

## Passaggio 5: salvataggio dell'intervallo di pagine in TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 In quest'ultimo passaggio, salviamo l'intervallo di pagine specificato in formato TIFF utilizzando il file`Save`metodo e passando il percorso al file di output con`.tiff` estensione, insieme alle opzioni di salvataggio specificate .

Ora puoi eseguire il codice sorgente per ottenere un intervallo specifico di pagine dal tuo documento e salvarle come file TIFF. I file risultanti verranno salvati nella directory specificata con i nomi "WorkingWithImageSaveOptions.MultipageTiff.tiff" per il documento completo e "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" per l'intervallo di pagine specificato.

### Esempio di codice sorgente di Get Tiff Page Range utilizzando Aspose.Words per .NET

```csharp 

// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità per ottenere una gamma di pagine TIFF con Aspose.Words per .NET. Abbiamo imparato come estrarre un intervallo specifico di pagine da un documento e salvarle come file TIFF.

Questa funzione è utile quando si desidera estrarre solo determinate pagine da un documento e salvarle in un formato immagine standard come TIFF. Puoi anche personalizzare le opzioni di compressione e risoluzione per ottenere file TIFF della migliore qualità.

Aspose.Words per .NET offre una vasta gamma di funzionalità avanzate per la manipolazione e la generazione di documenti. Ottenere un intervallo di pagine TIFF è uno dei tanti potenti strumenti che mette a tua disposizione.

Sentiti libero di integrare questa funzionalità nei tuoi progetti Aspose.Words per .NET per estrarre e salvare intervalli specifici di pagine dai tuoi documenti in formato TIFF.