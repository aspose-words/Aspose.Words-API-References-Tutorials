---
title: 在 Aspose.Words for Java 中保存文档中的图像
linktitle: 保存文档中的图像
second_title: Aspose.Words Java 文档处理 API
description: 通过我们全面的分步指南，了解如何使用 Aspose.Words for Java 保存文档中的图像。自定义格式、压缩等。
type: docs
weight: 17
url: /zh/java/document-loading-and-saving/saving-images-from-documents/
---

## 在 Aspose.Words for Java 中保存文档中的图像简介

在本教程中，我们将探讨如何使用 Aspose.Words for Java 保存文档中的图像。我们将介绍图像保存的各种场景和自定义选项。本指南提供了带有源代码示例的分步说明。

## 先决条件

在开始之前，请确保您已将 Aspose.Words for Java 库集成到您的项目中。您可以从以下位置下载：[这里](https://releases.aspose.com/words/java/).

## 第 1 步：使用阈值控制将图像保存为 TIFF

要将图像保存为带有阈值控制的 TIFF 格式，请按照下列步骤操作：

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## 步骤 2：将特定页面另存为多页 TIFF

要将特定页面另存为多页 TIFF，请使用以下代码：

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## 步骤 3：将图像另存为 1 BPP 索引 PNG

要将图像另存为 1 BPP 索引 PNG，请按照下列步骤操作：

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## 步骤 4：通过自定义将页面另存为 JPEG

要将特定页面保存为具有自定义选项的 JPEG，请使用以下代码：

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## 第5步：使用页面保存回调

您可以使用回调来自定义页面保存。这是一个例子：

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

## 在 Aspose.Words for Java 中保存文档图像的完整源代码

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
	//将“PageSet”设置为“0”以仅转换文档的第一页。
	options.setPageSet(new PageSet(0));
	//更改图像的亮度和对比度。
	//两者的评分范围均为 0-1，默认值为 0.5。
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	//更改水平分辨率。
	//对于 96dpi 的分辨率，这些属性的默认值为 96.0。
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

## 结论

您已经学习了如何使用 Aspose.Words for Java 保存文档中的图像。这些示例演示了图像保存的各种自定义选项，包括格式、压缩和回调使用。利用 Aspose.Words for Java 的强大功能探索更多可能性。

## 常见问题解答

### 使用 Aspose.Words for Java 保存时如何更改图像格式？

您可以通过在中指定所需的格式来更改图像格式`ImageSaveOptions`。例如，要另存为 PNG，请使用`SaveFormat.PNG`如代码所示：

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### 我可以自定义 TIFF 图像的压缩设置吗？

是的，您可以自定义 TIFF 图像压缩设置。例如，要将压缩方法设置为CCITT_3，请使用以下代码：

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### 如何将文档中的特定页面另存为单独的图像？

要将特定页面另存为图像，请使用`setPageSet`中的方法`ImageSaveOptions`。例如，要仅保存第一页，请设置`PageSet`到`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); //将第一页保存为图像
```

### 保存时如何将自定义设置应用于 JPEG 图像？

您可以使用以下命令将自定义设置应用于 JPEG 图像`ImageSaveOptions`。调整亮度、对比度和分辨率等属性。例如，要将亮度更改为 0.3，对比度更改为 0.7，请使用以下代码：

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### 如何使用回调来自定义图像保存？

要使用回调来自定义图像保存，请设置`PageSavingCallback`在`ImageSaveOptions`。创建一个类来实现`IPageSavingCallback`接口并覆盖`pageSaving`方法。

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

然后，创建一个类来实现`IPageSavingCallback`界面并自定义文件名和位置`pageSaving`方法。

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```