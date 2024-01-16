---
title: Richiamata di salvataggio della pagina
linktitle: Richiamata di salvataggio della pagina
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come personalizzare il salvataggio delle pagine dei documenti in immagini con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-imagesaveoptions/page-saving-callback/
---

In questo tutorial esploreremo il codice sorgente C# fornito per l'utilizzo del callback di salvataggio della pagina con le opzioni di salvataggio dell'immagine Aspose.Words per .NET. Questa funzionalità consente di eseguire azioni personalizzate quando si salva ciascuna pagina di un documento come immagine.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 In questo passaggio, configuriamo le opzioni di salvataggio dell'immagine creandone una nuova`ImageSaveOptions` oggetto. Specifichiamo il formato di backup desiderato, qui "Png" per il formato PNG. Noi usiamo`PageSet` per specificare l'intervallo di pagine da salvare, qui dalla prima all'ultima pagina del documento (`doc.PageCount - 1`). Abbiamo anche impostato`PageSavingCallback` a un'istanza di`HandlePageSavingCallback`, che è una classe personalizzata per gestire il callback di salvataggio della pagina.

## Passaggio 4: implementazione della richiamata di salvataggio della pagina

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implementa qui le tue azioni personalizzate
         // È possibile accedere alle informazioni sulla pagina tramite la proprietà "args.PageIndex".
         // Puoi anche modificare le opzioni di salvataggio per ciascuna pagina individualmente
     }
}
```

 In questo passaggio implementiamo il file`HandlePageSavingCallback` classe che implementa il`IPageSavingCallback` interfaccia. Puoi personalizzare questa classe aggiungendo le tue azioni specifiche nel file`PageSaving` metodo. È possibile accedere alle informazioni della pagina tramite`args.PageIndex` proprietà del`PageSavingArgs` oggetto passato come argomento.

## Passaggio 5: salvataggio delle pagine come immagini

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 In questo passaggio finale, salviamo ogni pagina del documento come immagine utilizzando il file`Save` metodo e passando il percorso del file di output con il metodo`.png` estensione, insieme alle opzioni di salvataggio specificate.

Ora puoi eseguire il codice sorgente per eseguire azioni personalizzate quando salvi ogni pagina del documento come immagine. Il file risultante verrà salvato nella directory specificata con il nome "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Codice sorgente di esempio per la richiamata di salvataggio della pagina utilizzando Aspose.Words per .NET


```csharp 
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità di callback di salvataggio della pagina con le opzioni di salvataggio delle immagini Aspose.Words per .NET. Abbiamo imparato come eseguire azioni personalizzate quando si salva ciascuna pagina di un documento come immagine.

Questa funzione è utile quando si desidera eseguire operazioni specifiche su ciascuna pagina durante la conversione in immagini. È possibile accedere alle informazioni della pagina e utilizzarle per personalizzare le opzioni di backup o eseguire altre elaborazioni specifiche della pagina.

Aspose.Words per .NET offre una vasta gamma di funzionalità avanzate per la manipolazione e la generazione di documenti. Il promemoria di salvataggio della pagina è uno dei tanti potenti strumenti che ti offre per personalizzare il processo di salvataggio delle pagine in immagini.