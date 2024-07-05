---
title: Aspose.Words for Java でカスタム バーコード ラベルを生成する
linktitle: カスタムバーコードラベルの生成
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java でカスタム バーコード ラベルを生成します。このステップ バイ ステップ ガイドでは、Aspose.Words for Java を使用してパーソナライズされたバーコード ソリューションを作成する方法を学習します。
type: docs
weight: 10
url: /ja/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Aspose.Words for Java でのカスタム バーコード ラベルの生成の概要

この包括的なガイドでは、Aspose.Words for Java を使用してカスタム バーコード ラベルを生成するプロセスを詳しく説明します。Aspose.Words for Java は、開発者が Word 文書をプログラムで操作できるようにする強力な API です。その注目すべき機能の 1 つはバーコード ラベルを操作できることで、カスタマイズされたバーコード ソリューションを必要とする企業や組織にとって貴重なツールとなっています。

## 前提条件

カスタム バーコード ラベルの生成の詳細に入る前に、前提条件が満たされていることを確認しましょう。

1. Java 開発環境: システムに Java と統合開発環境 (IDE) がインストールされていることを確認します。

2.  Aspose.Words for Java: Aspose.Words for Javaをダウンロードしてインストールします。[ここ](https://releases.aspose.com/words/java/).

3. Java の基礎知識: カスタム バーコード ラベルを作成するために Java コードを記述するため、Java プログラミングの知識が役立ちます。

## カスタムバーコードラベルの作成

それでは、Aspose.Words for Java を使用してカスタム バーコード ラベルの作成を始めましょう。プロセスをステップに分割し、各ステップの Java コード スニペットを提供します。

## バーコードの高さの設定

まず、バーコードの高さを twip (1/1440 インチ) で設定する必要があります。次に、この値をミリメートル (mm) に変換します。これを実行するコードは次のとおりです。

```java
	//入力値は1/1440インチ（twips）単位です
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	//mmに変換
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## バーコード画像の色変換

次に、バーコード画像の色を Word から Aspose.BarCode に変換します。入力色は「0xRRGGBB」(16 進数) の形式にする必要があります。変換のコードは次のとおりです。

```java
/// <要約>
/// バーコード画像の色を Word から Aspose.BarCode に変換します。
/// </要約>
/// <param name="入力カラー"></param>
/// <戻り値></戻り値>
private static Color convertColor(String inputColor) throws Exception {
	//入力範囲は「0x000000」から「0xFFFFFF」までです。
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## バーコードのスケール係数の変換

ここで、バーコードのスケーリング係数をパーセンテージから浮動小数点値に変換します。このスケーリング係数によってバーコードのサイズが決まります。変換のコードは次のとおりです。

```java
/// <要約>
/// バーコードのスケーリング係数をパーセントから浮動小数点数に変換します。
/// </要約>
/// <param name="スケーリング係数"></param>
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

このステップでは、`getBarcodeImage`メソッドは、指定されたパラメータに基づいてバーコード イメージを生成します。さまざまなバーコード タイプを処理し、色を設定し、寸法を調整するなどします。このメソッドのコードは次のとおりです。

```java
/// <要約>
/// IBarCodeGenerator インターフェイスの GetBarCodeImage() メソッドの実装。
/// </要約>
/// <param name="パラメータ"></param>
/// <戻り値></戻り値>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	//バーコードの種類と値が提供されているかどうかを確認します
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	//バーコードの種類に基づいてBarcodeGeneratorを作成する
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		//他のバーコードタイプをここで処理します
	}
	
	//バーコードテキストを設定する
	generator.setCodeText(parameters.getBarcodeValue());
	
	//バーコードの色を設定する
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
	
	//コードテキストの位置をカスタマイズする
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	//QRコードの追加調整
	final float SCALE = 2.4f; //Word バーコードを Aspose.BarCode に変換するための経験的スケーリング係数
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
	
	//バーコード画像を生成して返す
	return generator.generateBarCodeImage();
}
```

## GetOldBarcodeImage() メソッドの実装

このステップでは、`getOldBarcodeImage`このメソッドは、旧式のバーコードのバーコード イメージを生成します。ここでは、POSTNET などの特定のバーコード タイプを処理します。このメソッドのコードは次のとおりです。

```java
/// <要約>
/// IBarCodeGenerator インターフェイスの GetOldBarcodeImage() メソッドの実装。
/// </要約>
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
	//旧式のバーコード用のハードコードタイプ
	return generator.generateBarCodeImage();
}
```

## 結論

この記事では、Aspose.Words for Java を使用してカスタム バーコード ラベルを生成するプロセスについて説明しました。バーコードの高さの設定からバーコード生成メソッドの実装まで、重要な手順について説明しました。Aspose.Words for Java を使用すると、開発者は動的でカスタマイズされたバーコード ラベルを作成できるため、さまざまな業界にとって貴重なツールとなります。

## よくある質問

### 生成されたバーコードのサイズを調整するにはどうすればよいですか?

提供されているコード スニペットでバーコードのシンボルの高さとスケーリング係数を設定することで、生成されたバーコードのサイズを調整できます。これらのパラメータを使用すると、要件に応じてバーコードの寸法を制御できます。

### バーコードの色を変えることはできますか？

はい、コード内で前景色と背景色を指定することにより、バーコードの色を変更できます。このカスタマイズにより、バーコードの外観をドキュメントのデザインに合わせることができます。

### Aspose.Words for Java ではどのバーコード タイプがサポートされていますか?

Aspose.Words for Java は、QR コード、CODE128、CODE39、EAN8、EAN13、UPCA、UPCE、ITF14 など、さまざまなバーコード タイプをサポートしています。アプリケーションのニーズに合ったバーコード タイプを選択できます。

### 生成されたバーコードを Word 文書に統合するにはどうすればよいですか?

生成されたバーコードを Word 文書に統合するには、Aspose.Words for Java の文書操作機能を使用できます。バーコード イメージを文書の任意の場所に挿入できます。

### さらにカスタマイズできるサンプルコードはありますか?

はい、サンプル コード スニペットと追加のドキュメントは、Aspose.Words for Java のリファレンス サイトにあります。[Aspose.Words for Java API リファレンス](https://reference.aspose.com/words/java/).