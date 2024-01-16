---
title: Aspose.Words for Java でのカスタム バーコード ラベルの生成
linktitle: カスタムバーコードラベルの生成
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java でカスタム バーコード ラベルを生成します。このステップバイステップ ガイドでは、Aspose.Words for Java を使用してパーソナライズされたバーコード ソリューションを作成する方法を学びます。
type: docs
weight: 10
url: /ja/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Aspose.Words for Java でのカスタム バーコード ラベルの生成の概要

この包括的なガイドでは、Aspose.Words for Java を使用してカスタム バーコード ラベルを生成するプロセスについて詳しく説明します。 Aspose.Words for Java は、開発者が Word ドキュメントをプログラムで操作できるようにする強力な API です。その注目すべき機能の 1 つは、バーコード ラベルを操作できることであり、カスタマイズされたバーコード ソリューションを必要とする企業や組織にとって貴重なツールとなります。

## 前提条件

カスタム バーコード ラベルの生成の詳細に入る前に、前提条件が整っていることを確認してください。

1. Java 開発環境: システムに Java と統合開発環境 (IDE) がインストールされていることを確認してください。

2.  Aspose.Words for Java:Aspose.Words for Java を次からダウンロードしてインストールします。[ここ](https://releases.aspose.com/words/java/).

3. Java の基本知識: カスタム バーコード ラベルを作成する Java コードを作成するため、Java プログラミングに精通していると役立ちます。

## カスタムバーコードラベルの作成

それでは、Aspose.Words for Java を使用してカスタム バーコード ラベルの作成を開始しましょう。プロセスをステップに分割し、各ステップの Java コード スニペットを提供します。

## バーコードの高さの設定

まず、バーコードの高さを twip (1/1440 インチ) 単位で設定する必要があります。次に、この値をミリメートル (mm) に変換します。これを実現するコードは次のとおりです。

```java
	//入力値は 1/1440 インチ (twip) 単位です。
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// mmに変換
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## バーコード画像の色の変換

次に、バーコード画像の色を Word から Aspose.BarCode に変換します。入力カラーは「0xRRGGBB」(16 進数) の形式である必要があります。変換のコードは次のとおりです。

```java
/// <概要>
/// バーコード画像の色を Word から Aspose.BarCode に変換します。
/// </概要>
///<param name="inputColor"></param>
/// <戻り値></戻り値>
private static Color convertColor(String inputColor) throws Exception {
	// 「0x000000」から「0xFFFFFF」までを入力してください。
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## バーコード倍率の変換

ここで、バーコードの倍率をパーセンテージから浮動小数点値に変換します。この倍率によってバーコードのサイズが決まります。変換のコードは次のとおりです。

```java
/// <概要>
/// バーコードのスケール係数をパーセントから浮動小数点数に変換します。
/// </概要>
///<param name="scalingFactor"></param>
/// <戻り値></戻り値>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## GetBarCodeImage() メソッドの実装

このステップでは、`getBarcodeImage`メソッド。指定されたパラメーターに基づいてバーコード画像を生成します。さまざまなバーコード タイプの処理、色の設定、寸法の調整などを行います。このメソッドのコードは次のとおりです。

```java
/// <概要>
/// IBarCodeGenerator インターフェイスの GetBarCodeImage() メソッドの実装。
/// </概要>
/// <param name="パラメータ"></param>
/// <戻り値></戻り値>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	//バーコードのタイプと値が指定されているかどうかを確認します
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	//バーコードの種類に基づいて BarcodeGenerator を作成する
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		//他のバーコードタイプはここで処理します
	}
	
	//バーコードテキストを設定する
	generator.setCodeText(parameters.getBarcodeValue());
	
	//バーコードの色の設定
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	//シンボルの高さと寸法を設定する
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//コードテキストの場所をカスタマイズする
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	//QRコードの追加調整
	final float SCALE = 2.4f; //Word バーコードを Aspose.BarCode に変換するための経験的なスケーリング係数
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	//スケーリング係数を適用する
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//バーコード画像を生成して返します
	return generator.generateBarCodeImage();
}
```

## GetOldBarcodeImage() メソッドの実装

このステップでは、`getOldBarcodeImage`このメソッドは、昔ながらのバーコードのバーコード画像を生成します。ここでは、POSTNET などの特定のバーコード タイプを処理します。このメソッドのコードは次のとおりです。

```java
/// <概要>
/// IBarCodeGenerator インターフェイスの GetOldBarcodeImage() メソッドの実装。
/// </概要>
/// <param name="パラメータ"></param>
/// <戻り値></戻り値>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	//昔ながらのバーコードのハードコード タイプ
	return generator.generateBarCodeImage();
}
```

## 結論

この記事では、Aspose.Words for Java を使用してカスタム バーコード ラベルを生成するプロセスについて説明しました。バーコードの高さの設定からバーコード生成方法の実装まで、重要な手順を説明しました。 Aspose.Words for Java を使用すると、開発者は動的でカスタマイズされたバーコード ラベルを作成できるため、さまざまな業界にとって貴重なツールになります。

## よくある質問

### 生成されたバーコードのサイズを調整するにはどうすればよいですか?

提供されたコード スニペットでバーコードのシンボルの高さと倍率を設定することで、生成されるバーコードのサイズを調整できます。これらのパラメータを使用すると、要件に応じてバーコードの寸法を制御できます。

### バーコードの色を変更できますか?

はい、コード内で前景色と背景色を指定することで、バーコードの色を変更できます。このカスタマイズにより、バーコードの外観をドキュメントのデザインと一致させることができます。

### Aspose.Words for Java ではどのバーコード タイプがサポートされていますか?

Aspose.Words for Java は、QR コード、CODE128、CODE39、EAN8、EAN13、UPCA、UPCE、ITF14 などを含むさまざまなバーコード タイプをサポートします。アプリケーションのニーズに合わせてバーコードの種類を選択できます。

### 生成されたバーコードを Word 文書に統合するにはどうすればよいですか?

生成されたバーコードを Word 文書に統合するには、Aspose.Words for Java の文書操作機能を使用できます。バーコード画像を文書内の任意の場所に挿入できます。

### さらにカスタマイズできるサンプル コードはありますか?

はい、サンプル コード スニペットと追加ドキュメントは、Aspose.Words for Java のリファレンス サイトで見つけることができます。[Aspose.Words for Java API リファレンス](https://reference.aspose.com/words/java/).