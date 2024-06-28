---
title: Сохранение изображений из документов в Aspose.Words для Java
linktitle: Сохранение изображений из документов
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как сохранять изображения из документов с помощью Aspose.Words для Java, с помощью нашего подробного пошагового руководства. Настраивайте форматы, сжатие и многое другое.
type: docs
weight: 17
url: /ru/java/document-loading-and-saving/saving-images-from-documents/
---

## Введение в сохранение изображений из документов в Aspose.Words для Java

В этом уроке мы рассмотрим, как сохранять изображения из документов с помощью Aspose.Words для Java. Мы рассмотрим различные сценарии и варианты настройки сохранения изображений. В этом руководстве представлены пошаговые инструкции с примерами исходного кода.

## Предварительные условия

 Прежде чем начать, убедитесь, что в ваш проект интегрирована библиотека Aspose.Words for Java. Вы можете скачать его с[здесь](https://releases.aspose.com/words/java/).

## Шаг 1. Сохранение изображений в формате TIFF с контролем порога

Чтобы сохранить изображения в формате TIFF с пороговым контролем, выполните следующие действия:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## Шаг 2. Сохраните определенную страницу в многостраничном формате TIFF.

Чтобы сохранить определенную страницу в виде многостраничного TIFF, используйте следующий код:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## Шаг 3. Сохранение изображений в формате PNG с индексом 1 BPP

Чтобы сохранить изображения в формате PNG с индексом 1 BPP, выполните следующие действия:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## Шаг 4. Сохраните страницу в формате JPEG с настройкой

Чтобы сохранить определенную страницу в формате JPEG с возможностью настройки, используйте этот код:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## Шаг 5. Использование обратного вызова для сохранения страницы

Вы можете использовать обратный вызов для настройки сохранения страницы. Вот пример:

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

## Полный исходный код для сохранения изображений из документов в Aspose.Words для Java

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
	// Установите для параметра «PageSet» значение «0», чтобы преобразовать только первую страницу документа.
	options.setPageSet(new PageSet(0));
	// Измените яркость и контрастность изображения.
	// Оба имеют шкалу 0–1 и по умолчанию равны 0,5.
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	// Измените горизонтальное разрешение.
	// Значение по умолчанию для этих свойств — 96,0 для разрешения 96 точек на дюйм.
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

## Заключение

Вы узнали, как сохранять изображения из документов с помощью Aspose.Words для Java. Эти примеры демонстрируют различные варианты настройки сохранения изображений, включая формат, сжатие и использование обратного вызова. Откройте для себя больше возможностей с помощью Aspose.Words для мощных возможностей Java.

## Часто задаваемые вопросы

### Как изменить формат изображения при сохранении с помощью Aspose.Words для Java?

 Вы можете изменить формат изображения, указав нужный формат в поле`ImageSaveOptions` . Например, чтобы сохранить в формате PNG, используйте`SaveFormat.PNG` как показано в коде:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### Могу ли я настроить параметры сжатия изображений TIFF?

Да, вы можете настроить параметры сжатия изображений TIFF. Например, чтобы установить метод сжатия CCITT_3, используйте следующий код:

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### Как сохранить определенную страницу документа как отдельное изображение?

 Чтобы сохранить определенную страницу в виде изображения, используйте команду`setPageSet`метод в`ImageSaveOptions` . Например, чтобы сохранить только первую страницу, установите`PageSet` к`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); // Сохраните первую страницу как изображение
```

### Как применить пользовательские настройки к изображениям JPEG при сохранении?

Вы можете применить пользовательские настройки к изображениям JPEG, используя`ImageSaveOptions`. Настройте такие свойства, как яркость, контрастность и разрешение. Например, чтобы изменить яркость на 0,3 и контрастность на 0,7, используйте этот код:

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### Как я могу использовать обратный вызов для настройки сохранения изображений?

 Чтобы использовать обратный вызов для настройки сохранения изображений, установите параметр`PageSavingCallback` в`ImageSaveOptions` . Создайте класс, реализующий`IPageSavingCallback` интерфейс и переопределить`pageSaving` метод.

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

 Затем создайте класс, реализующий`IPageSavingCallback` интерфейс и настройте имя и местоположение файла в`pageSaving` метод.

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```