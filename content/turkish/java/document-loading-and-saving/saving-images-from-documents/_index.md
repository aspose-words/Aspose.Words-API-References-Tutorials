---
title: Aspose.Words for Java'da Belgelerdeki Görüntüleri Kaydetme
linktitle: Belgelerden Görüntü Kaydetme
second_title: Aspose.Words Java Belge İşleme API'si
description: Kapsamlı adım adım kılavuzumuzla Aspose.Words for Java kullanarak belgelerden görüntüleri nasıl kaydedeceğinizi öğrenin. Formatları, sıkıştırmayı ve daha fazlasını özelleştirin.
type: docs
weight: 17
url: /tr/java/document-loading-and-saving/saving-images-from-documents/
---

## Aspose.Words for Java'da Belgelerden Görüntü Kaydetmeye Giriş

Bu derste Aspose.Words for Java kullanarak belgelerdeki görüntülerin nasıl kaydedileceğini inceleyeceğiz. Görüntü kaydetmeye yönelik çeşitli senaryoları ve özelleştirme seçeneklerini ele alacağız. Bu kılavuz, kaynak kodu örnekleriyle adım adım talimatlar sağlar.

## Önkoşullar

 Başlamadan önce Aspose.Words for Java kütüphanesinin projenize entegre olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/).

## Adım 1: Eşik Kontrolüyle Görüntüleri TIFF Olarak Kaydetme

Görüntüleri eşik kontrolüyle TIFF formatında kaydetmek için şu adımları izleyin:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## Adım 2: Belirli Bir Sayfayı Çok Sayfalı TIFF Olarak Kaydetme

Belirli bir sayfayı çok sayfalı TIFF olarak kaydetmek için aşağıdaki kodu kullanın:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## Adım 3: Görüntüleri 1 BPP Dizinli PNG Olarak Kaydetme

Görüntüleri 1 BPP indeksli PNG olarak kaydetmek için şu adımları izleyin:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## Adım 4: Özelleştirmeyle Bir Sayfayı JPEG Olarak Kaydetme

Belirli bir sayfayı özelleştirme seçenekleriyle JPEG olarak kaydetmek için bu kodu kullanın:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## Adım 5: Sayfa Kaydederek Geri Aramayı Kullanma

Sayfa kaydetmeyi özelleştirmek için geri aramayı kullanabilirsiniz. İşte bir örnek:

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

## Aspose.Words for Java'daki Belgelerdeki Görüntüleri Kaydetmek İçin Tam Kaynak Kodu

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
	// Bir belgenin yalnızca ilk sayfasını dönüştürmek için "PageSet"i "0" olarak ayarlayın.
	options.setPageSet(new PageSet(0));
	// Görüntünün parlaklığını ve kontrastını değiştirin.
	// Her ikisi de 0-1 ölçeğindedir ve varsayılan olarak 0,5'tir.
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	// Yatay çözünürlüğü değiştirin.
	// Bu özelliklerin varsayılan değeri 96 dpi çözünürlük için 96,0'dır.
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

## Çözüm

Aspose.Words for Java kullanarak belgelerdeki görüntüleri nasıl kaydedeceğinizi öğrendiniz. Bu örnekler, format, sıkıştırma ve geri arama kullanımı da dahil olmak üzere görüntü kaydetmeye yönelik çeşitli özelleştirme seçeneklerini gösterir. Aspose.Words for Java'nın güçlü yetenekleriyle daha fazla olasılığı keşfedin.

## SSS'ler

### Aspose.Words for Java ile kaydederken görüntü formatını nasıl değiştiririm?

 İstenilen formatı belirterek resim formatını değiştirebilirsiniz.`ImageSaveOptions` . Örneğin, PNG olarak kaydetmek için şunu kullanın:`SaveFormat.PNG` kodda gösterildiği gibi:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### TIFF görüntüleri için sıkıştırma ayarlarını özelleştirebilir miyim?

Evet, TIFF görüntü sıkıştırma ayarlarını özelleştirebilirsiniz. Örneğin, sıkıştırma yöntemini CCITT_3 olarak ayarlamak için aşağıdaki kodu kullanın:

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### Bir belgedeki belirli bir sayfayı ayrı bir görüntü olarak nasıl kaydedebilirim?

 Belirli bir sayfayı resim olarak kaydetmek için`setPageSet`yöntem`ImageSaveOptions` . Örneğin yalnızca ilk sayfayı kaydetmek için`PageSet` ile`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); // İlk sayfayı resim olarak kaydedin
```

### Kaydederken özel ayarları JPEG görüntülerine nasıl uygularım?

kullanarak JPEG görüntülere özel ayarlar uygulayabilirsiniz.`ImageSaveOptions`. Parlaklık, kontrast ve çözünürlük gibi özellikleri ayarlayın. Örneğin, parlaklığı 0,3'e ve kontrastı 0,7'ye değiştirmek için şu kodu kullanın:

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### Görüntü kaydetmeyi özelleştirmek için geri aramayı nasıl kullanabilirim?

 Görüntü kaydetmeyi özelleştirmek amacıyla geri aramayı kullanmak için`PageSavingCallback` içinde`ImageSaveOptions` . uygulayan bir sınıf oluşturun.`IPageSavingCallback` arayüzü geçersiz kılın ve`pageSaving` yöntem.

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

 Daha sonra bunu uygulayan bir sınıf oluşturun.`IPageSavingCallback` arayüzde dosya adını ve konumunu özelleştirin`pageSaving` yöntem.

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```