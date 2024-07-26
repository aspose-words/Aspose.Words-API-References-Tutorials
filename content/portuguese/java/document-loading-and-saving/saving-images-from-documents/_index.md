---
title: Salvando imagens de documentos em Aspose.Words for Java
linktitle: Salvando imagens de documentos
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como salvar imagens de documentos usando Aspose.Words for Java com nosso guia passo a passo abrangente. Personalize formatos, compactação e muito mais.
type: docs
weight: 17
url: /pt/java/document-loading-and-saving/saving-images-from-documents/
---

## Introdução ao salvamento de imagens de documentos em Aspose.Words para Java

Neste tutorial, exploraremos como salvar imagens de documentos usando Aspose.Words for Java. Abordaremos vários cenários e opções de personalização para salvar imagens. Este guia fornece instruções passo a passo com exemplos de código-fonte.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Words for Java integrada ao seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/words/java/).

## Etapa 1: Salvar imagens como TIFF com controle de limite

Para salvar imagens no formato TIFF com controle de limite, siga estas etapas:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## Etapa 2: Salvar uma página específica como TIFF de várias páginas

Para salvar uma página específica como TIFF de várias páginas, use o seguinte código:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## Etapa 3: Salvar imagens como PNG indexado de 1 BPP

Para salvar imagens como PNG indexado de 1 BPP, siga estas etapas:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## Etapa 4: Salvar uma página como JPEG com personalização

Para salvar uma página específica como JPEG com opções de personalização, use este código:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## Etapa 5: usando retorno de chamada para salvar página

Você pode usar um retorno de chamada para personalizar o salvamento da página. Aqui está um exemplo:

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

## Código-fonte completo para salvar imagens de documentos em Aspose.Words for Java

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
	// Defina “PageSet” como “0” para converter apenas a primeira página de um documento.
	options.setPageSet(new PageSet(0));
	// Altere o brilho e o contraste da imagem.
	// Ambos estão em uma escala de 0 a 1 e estão em 0,5 por padrão.
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	// Altere a resolução horizontal.
	// O valor padrão para essas propriedades é 96,0, para uma resolução de 96 dpi.
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

## Conclusão

Você aprendeu como salvar imagens de documentos usando Aspose.Words for Java. Estes exemplos demonstram várias opções de personalização para salvar imagens, incluindo formato, compactação e uso de retorno de chamada. Explore mais possibilidades com os poderosos recursos do Aspose.Words for Java.

## Perguntas frequentes

### Como altero o formato da imagem ao salvar com Aspose.Words for Java?

 Você pode alterar o formato da imagem especificando o formato desejado no campo`ImageSaveOptions` . Por exemplo, para salvar como PNG, use`SaveFormat.PNG` conforme mostrado no código:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### Posso personalizar as configurações de compactação de imagens TIFF?

Sim, você pode personalizar as configurações de compactação de imagem TIFF. Por exemplo, para definir o método de compactação como CCITT_3, use o seguinte código:

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### Como posso salvar uma página específica de um documento como uma imagem separada?

 Para salvar uma página específica como imagem, use o`setPageSet`método em`ImageSaveOptions` . Por exemplo, para salvar apenas a primeira página, defina o`PageSet` para`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); // Salve a primeira página como uma imagem
```

### Como aplico configurações personalizadas a imagens JPEG ao salvar?

Você pode aplicar configurações personalizadas a imagens JPEG usando`ImageSaveOptions`. Ajuste propriedades como brilho, contraste e resolução. Por exemplo, para alterar o brilho para 0,3 e o contraste para 0,7, use este código:

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### Como posso usar um retorno de chamada para personalizar o salvamento de imagens?

 Para usar um retorno de chamada para personalizar o salvamento de imagens, defina o`PageSavingCallback` em`ImageSaveOptions` . Crie uma classe que implemente o`IPageSavingCallback` interface e substituir o`pageSaving` método.

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

 Em seguida, crie uma classe que implemente o`IPageSavingCallback` interface e personalize o nome do arquivo e a localização na`pageSaving` método.

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```