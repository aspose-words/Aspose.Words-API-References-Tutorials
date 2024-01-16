---
title: Aspose.Words for Java でドキュメントから画像を保存する
linktitle: ドキュメントから画像を保存する
second_title: Aspose.Words Java ドキュメント処理 API
description: 包括的なステップバイステップ ガイドで、Aspose.Words for Java を使用してドキュメントから画像を保存する方法を学びましょう。形式や圧縮などをカスタマイズします。
type: docs
weight: 17
url: /ja/java/document-loading-and-saving/saving-images-from-documents/
---

## Aspose.Words for Java でのドキュメントからの画像の保存の概要

このチュートリアルでは、Aspose.Words for Java を使用してドキュメントから画像を保存する方法を説明します。画像保存に関するさまざまなシナリオとカスタマイズ オプションについて説明します。このガイドでは、ソース コードの例を使用して段階的な手順を説明します。

## 前提条件

始める前に、Aspose.Words for Java ライブラリがプロジェクトに統合されていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/words/java/).

## ステップ 1: しきい値制御を使用して画像を TIFF として保存する

しきい値制御を使用して画像を TIFF 形式で保存するには、次の手順に従います。

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## ステップ 2: 特定のページをマルチページ TIFF として保存する

特定のページをマルチページ TIFF として保存するには、次のコードを使用します。

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## ステップ 3: 画像を 1 BPP インデックス付き PNG として保存する

画像を 1 BPP インデックス付き PNG として保存するには、次の手順に従います。

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## ステップ 4: カスタマイズしてページを JPEG として保存する

カスタマイズ オプションを使用して特定のページを JPEG として保存するには、次のコードを使用します。

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## ステップ 5: ページ保存コールバックの使用

コールバックを使用してページ保存をカスタマイズできます。以下に例を示します。

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

## Aspose.Words for Java でドキュメントから画像を保存するための完全なソース コード

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
	//ドキュメントの最初のページのみを変換するには、「PageSet」を「0」に設定します。
	options.setPageSet(new PageSet(0));
	//画像の明るさとコントラストを変更します。
	//どちらも 0 ～ 1 のスケールで、デフォルトでは 0.5 です。
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	//水平解像度を変更します。
	//これらのプロパティのデフォルト値は 96.0 (解像度 96dpi) です。
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

## 結論

Aspose.Words for Java を使用してドキュメントから画像を保存する方法を学習しました。これらの例は、形式、圧縮、コールバックの使用など、画像保存のためのさまざまなカスタマイズ オプションを示しています。 Aspose.Words for Java の強力な機能を使用して、さらなる可能性を探ってください。

## よくある質問

### Aspose.Words for Java で保存するときに画像形式を変更するにはどうすればよいですか?

画像フォーマットを変更するには、希望のフォーマットを指定します。`ImageSaveOptions` 。たとえば、PNG として保存するには、次を使用します。`SaveFormat.PNG`コードに示すように:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### TIFF 画像の圧縮設定をカスタマイズできますか?

はい、TIFF 画像圧縮設定をカスタマイズできます。たとえば、圧縮方法を CCITT_3 に設定するには、次のコードを使用します。

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### ドキュメントの特定のページを別の画像として保存するにはどうすればよいですか?

特定のページを画像として保存するには、`setPageSet`のメソッド`ImageSaveOptions` 。たとえば、最初のページだけを保存するには、`PageSet`に`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); //最初のページを画像として保存する
```

### 保存時に JPEG 画像にカスタム設定を適用するにはどうすればよいですか?

次を使用して JPEG 画像にカスタム設定を適用できます。`ImageSaveOptions`。明るさ、コントラスト、解像度などのプロパティを調整します。たとえば、明るさを 0.3 に、コントラストを 0.7 に変更するには、次のコードを使用します。

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### 画像保存をカスタマイズするためにコールバックを使用するにはどうすればよいですか?

画像保存をカスタマイズするためにコールバックを使用するには、`PageSavingCallback`で`ImageSaveOptions` 。を実装するクラスを作成します。`IPageSavingCallback`インターフェースを作成し、オーバーライドします`pageSaving`方法。

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

次に、を実装するクラスを作成します。`IPageSavingCallback`インターフェースを作成し、ファイル名と場所をカスタマイズします。`pageSaving`方法。

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```