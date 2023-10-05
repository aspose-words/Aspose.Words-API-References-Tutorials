---
title: Speichern von Bildern aus Dokumenten in Aspose.Words für Java
linktitle: Bilder aus Dokumenten speichern
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie in unserer umfassenden Schritt-für-Schritt-Anleitung, wie Sie Bilder aus Dokumenten mit Aspose.Words für Java speichern. Passen Sie Formate, Komprimierung und mehr an.
type: docs
weight: 17
url: /de/java/document-loading-and-saving/saving-images-from-documents/
---

## Einführung in das Speichern von Bildern aus Dokumenten in Aspose.Words für Java

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für Java Bilder aus Dokumenten speichern. Wir werden verschiedene Szenarien und Anpassungsoptionen für das Speichern von Bildern behandeln. Dieses Handbuch enthält Schritt-für-Schritt-Anleitungen mit Quellcode-Beispielen.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Words for Java-Bibliothek in Ihr Projekt integriert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/words/java/).

## Schritt 1: Bilder als TIFF mit Schwellenwertkontrolle speichern

Um Bilder im TIFF-Format mit Schwellenwertkontrolle zu speichern, gehen Sie folgendermaßen vor:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## Schritt 2: Speichern einer bestimmten Seite als mehrseitiges TIFF

Um eine bestimmte Seite als mehrseitiges TIFF zu speichern, verwenden Sie den folgenden Code:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## Schritt 3: Bilder als 1 BPP-indiziertes PNG speichern

Um Bilder als 1 BPP indiziertes PNG zu speichern, gehen Sie folgendermaßen vor:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## Schritt 4: Speichern einer Seite als JPEG mit Anpassung

Um eine bestimmte Seite als JPEG mit Anpassungsoptionen zu speichern, verwenden Sie diesen Code:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## Schritt 5: Verwenden des Seitenspeicherrückrufs

Sie können einen Rückruf verwenden, um das Speichern der Seite anzupassen. Hier ist ein Beispiel:

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

## Vollständiger Quellcode zum Speichern von Bildern aus Dokumenten in Aspose.Words für Java

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
	// Setzen Sie „PageSet“ auf „0“, um nur die erste Seite eines Dokuments zu konvertieren.
	options.setPageSet(new PageSet(0));
	// Ändern Sie die Helligkeit und den Kontrast des Bildes.
	// Beide liegen auf einer Skala von 0 bis 1 und liegen standardmäßig bei 0,5.
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	// Ändern Sie die horizontale Auflösung.
	// Der Standardwert für diese Eigenschaften ist 96,0 für eine Auflösung von 96 dpi.
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

## Abschluss

Sie haben gelernt, wie Sie mit Aspose.Words für Java Bilder aus Dokumenten speichern. Diese Beispiele veranschaulichen verschiedene Anpassungsoptionen für das Speichern von Bildern, einschließlich Format, Komprimierung und Rückrufverwendung. Entdecken Sie mehr Möglichkeiten mit Aspose.Words für die leistungsstarken Funktionen von Java.

## FAQs

### Wie ändere ich das Bildformat beim Speichern mit Aspose.Words für Java?

 Sie können das Bildformat ändern, indem Sie das gewünschte Format im angeben`ImageSaveOptions` . Um beispielsweise als PNG zu speichern, verwenden Sie`SaveFormat.PNG` wie im Code gezeigt:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### Kann ich die Komprimierungseinstellungen für TIFF-Bilder anpassen?

Ja, Sie können die Einstellungen für die TIFF-Bildkomprimierung anpassen. Um beispielsweise die Komprimierungsmethode auf CCITT_3 festzulegen, verwenden Sie den folgenden Code:

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### Wie kann ich eine bestimmte Seite eines Dokuments als separates Bild speichern?

 Um eine bestimmte Seite als Bild zu speichern, verwenden Sie die`setPageSet`Methode in`ImageSaveOptions` . Um beispielsweise nur die erste Seite zu speichern, legen Sie fest`PageSet` Zu`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); // Speichern Sie die erste Seite als Bild
```

### Wie wende ich beim Speichern benutzerdefinierte Einstellungen auf JPEG-Bilder an?

Mit können Sie benutzerdefinierte Einstellungen auf JPEG-Bilder anwenden`ImageSaveOptions`. Passen Sie Eigenschaften wie Helligkeit, Kontrast und Auflösung an. Um beispielsweise die Helligkeit auf 0,3 und den Kontrast auf 0,7 zu ändern, verwenden Sie diesen Code:

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### Wie kann ich einen Rückruf zum Anpassen der Bildspeicherung verwenden?

 Um einen Rückruf zum Anpassen der Bildspeicherung zu verwenden, legen Sie fest`PageSavingCallback` In`ImageSaveOptions` . Erstellen Sie eine Klasse, die das implementiert`IPageSavingCallback` Schnittstelle und überschreiben Sie die`pageSaving` Methode.

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

 Erstellen Sie dann eine Klasse, die das implementiert`IPageSavingCallback` Schnittstelle und passen Sie den Dateinamen und den Speicherort in der an`pageSaving` Methode.

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```