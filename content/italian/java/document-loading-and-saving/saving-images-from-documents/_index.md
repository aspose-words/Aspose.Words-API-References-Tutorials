---
title: Salvataggio di immagini da documenti in Aspose.Words per Java
linktitle: Salvataggio di immagini da documenti
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come salvare immagini dai documenti utilizzando Aspose.Words per Java con la nostra guida passo passo completa. Personalizza formati, compressione e altro ancora.
type: docs
weight: 17
url: /it/java/document-loading-and-saving/saving-images-from-documents/
---

## Introduzione al salvataggio di immagini da documenti in Aspose.Words per Java

In questo tutorial esploreremo come salvare immagini da documenti utilizzando Aspose.Words per Java. Tratteremo vari scenari e opzioni di personalizzazione per il salvataggio delle immagini. Questa guida fornisce istruzioni dettagliate con esempi di codice sorgente.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Words per Java integrata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/words/java/).

## Passaggio 1: salvataggio delle immagini come TIFF con controllo soglia

Per salvare le immagini in formato TIFF con controllo della soglia, attenersi alla seguente procedura:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## Passaggio 2: salvataggio di una pagina specifica come TIFF multipagina

Per salvare una pagina specifica come TIFF multipagina, utilizzare il seguente codice:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## Passaggio 3: salvataggio delle immagini come PNG indicizzato 1 BPP

Per salvare le immagini come PNG indicizzato 1 BPP, attenersi alla seguente procedura:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## Passaggio 4: salvataggio di una pagina come JPEG con personalizzazione

Per salvare una pagina specifica come JPEG con opzioni di personalizzazione, utilizza questo codice:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## Passaggio 5: utilizzo della richiamata per il salvataggio della pagina

È possibile utilizzare una richiamata per personalizzare il salvataggio della pagina. Ecco un esempio:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
doc.save("Your Directory Path" + "PageSavingCallback.png", imageSaveOptions);
```

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```

## Codice sorgente completo per salvare immagini da documenti in Aspose.Words per Java

```java
public void exposeThresholdControlForTiffBinarization() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
	{
		saveOptions.setTiffCompression(TiffCompression.CCITT_3);
		saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
		saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
		saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
}
@Test
public void getTiffPageRange() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
	{
		saveOptions.setPageSet(new PageSet(new PageRange(0, 1))); saveOptions.setTiffCompression(TiffCompression.CCITT_4); saveOptions.setResolution(160f);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
}
@Test
public void format1BppIndexed() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
	{
		saveOptions.setPageSet(new PageSet(1));
		saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
		saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
}
@Test
public void getJpegPageRange() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
	// Impostare "PageSet" su "0" per convertire solo la prima pagina di un documento.
	options.setPageSet(new PageSet(0));
	// Modifica la luminosità e il contrasto dell'immagine.
	// Entrambi sono su una scala 0-1 e sono a 0,5 per impostazione predefinita.
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	// Modificare la risoluzione orizzontale.
	// Il valore predefinito per queste proprietà è 96,0, per una risoluzione di 96 dpi.
	options.setHorizontalResolution(72f);
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
}
@Test
public static void pageSavingCallback() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
	{
		imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
		imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
}
private static class HandlePageSavingCallback implements IPageSavingCallback
{
	public void pageSaving(PageSavingArgs args)
	{
		args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
	}
```

## Conclusione

Hai imparato come salvare immagini dai documenti utilizzando Aspose.Words per Java. Questi esempi dimostrano varie opzioni di personalizzazione per il salvataggio delle immagini, inclusi formato, compressione e utilizzo del callback. Esplora più possibilità con Aspose.Words per le potenti funzionalità di Java.

## Domande frequenti

### Come posso modificare il formato dell'immagine durante il salvataggio con Aspose.Words per Java?

 È possibile modificare il formato dell'immagine specificando il formato desiderato nel file`ImageSaveOptions` . Ad esempio, per salvare come PNG, utilizzare`SaveFormat.PNG` come mostrato nel codice:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### Posso personalizzare le impostazioni di compressione per le immagini TIFF?

Sì, puoi personalizzare le impostazioni di compressione delle immagini TIFF. Ad esempio, per impostare il metodo di compressione su CCITT_3, utilizzare il seguente codice:

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### Come posso salvare una pagina specifica da un documento come immagine separata?

 Per salvare una pagina specifica come immagine, utilizzare il file`setPageSet`metodo dentro`ImageSaveOptions` . Ad esempio, per salvare solo la prima pagina, impostare il file`PageSet` A`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); // Salva la prima pagina come immagine
```

### Come posso applicare le impostazioni personalizzate alle immagini JPEG durante il salvataggio?

È possibile applicare impostazioni personalizzate alle immagini JPEG utilizzando`ImageSaveOptions`. Regola proprietà come luminosità, contrasto e risoluzione. Ad esempio, per modificare la luminosità su 0,3 e il contrasto su 0,7, utilizza questo codice:

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### Come posso utilizzare una richiamata per personalizzare il salvataggio delle immagini?

 Per utilizzare una richiamata per personalizzare il salvataggio delle immagini, impostare il file`PageSavingCallback` In`ImageSaveOptions` . Crea una classe che implementa il`IPageSavingCallback` interfaccia e sovrascrivere il file`pageSaving` metodo.

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

 Quindi, crea una classe che implementi il file`IPageSavingCallback` interfaccia e personalizzare il nome e il percorso del file nel file`pageSaving` metodo.

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```