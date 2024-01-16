---
title: 在 Aspose.Words for Java 中產生自訂條碼標籤
linktitle: 產生自訂條碼標籤
second_title: Aspose.Words Java 文件處理 API
description: 在 Aspose.Words for Java 中產生自訂條碼標籤。在此逐步指南中了解如何使用 Aspose.Words for Java 建立個人化條碼解決方案。
type: docs
weight: 10
url: /zh-hant/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## 在 Aspose.Words for Java 中產生自訂條碼標籤簡介

在本綜合指南中，我們將深入研究使用 Aspose.Words for Java 產生自訂條碼標籤的過程。 Aspose.Words for Java 是一個功能強大的 API，允許開發人員以程式設計方式操作 Word 文件。其顯著的功能之一是能夠使用條碼標籤，這使其成為需要客製化條碼解決方案的企業和組織的寶貴工具。

## 先決條件

在我們深入了解產生自訂條碼標籤的詳細資訊之前，我們先確保滿足先決條件：

1. Java 開發環境：確保您的系統上安裝了 Java 和整合開發環境 (IDE)。

2.  Aspose.Words for Java：從下列位置下載並安裝 Aspose.Words for Java：[這裡](https://releases.aspose.com/words/java/).

3. Java 基本：熟悉 Java 程式設計將會很有幫助，因為我們將編寫 Java 程式碼來建立自訂條碼標籤。

## 建立自訂條碼標籤

現在，讓我們開始使用 Aspose.Words for Java 建立自訂條碼標籤。我們將把該過程分解為多個步驟，並為每個步驟提供 Java 程式碼片段。

## 設定條碼高度

首先，我們需要以緹（1/1440 英吋）為單位設定條碼的高度。然後我們將該值轉換為毫米 (mm)。這是完成此操作的程式碼：

```java
	//輸入值的單位為 1/1440 英吋（緹）
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	//轉換為毫米
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## 轉換條碼影像顏色

接下來，我們將把條碼圖片顏色從 Word 轉換為 Aspose.BarCode。輸入顏色的格式應為“0xRRGGBB”（十六進位）。這是轉換的程式碼：

```java
/// <摘要>
/// 將條碼圖片顏色從 Word 轉換為 Aspose.BarCode。
/// </摘要>
/// <參數名稱=“inputColor”></參數>
/// <返回></返回>
private static Color convertColor(String inputColor) throws Exception {
	//輸入應從“0x000000”到“0xFFFFFF”
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## 轉換條碼縮放因子

現在，我們將條碼縮放因子從百分比轉換為浮點數值。此縮放因子決定了條碼的大小。這是轉換的程式碼：

```java
/// <摘要>
/// 將條碼縮放因子從百分比轉換為浮點數。
/// </摘要>
/// <param name="scalingFactor"></param>
/// <返回></返回>
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

## 實作 GetBarCodeImage() 方法

在此步驟中，我們將實現`getBarcodeImage`方法，根據提供的參數產生條碼影像。我們將處理不同的條碼類型、設定顏色、調整尺寸等等。這是該方法的程式碼：

```java
/// <摘要>
/// IBarCodeGenerator 介面的 GetBarCodeImage() 方法的實作。
/// </摘要>
/// <參數名稱=“參數”></參數>
/// <返回></返回>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	//檢查是否提供了條碼類型和值
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	//根據條碼類型建立BarcodeGenerator
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		//在這裡處理其他條碼類型
	}
	
	//設定條碼文字
	generator.setCodeText(parameters.getBarcodeValue());
	
	//設定條碼顏色
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	//設定符號高度和尺寸
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//自訂程式碼文字位置
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	//二維碼的額外調整
	final float SCALE = 2.4f; //將 Word 條碼轉換為 Aspose.BarCode 的經驗縮放因子
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
	
	//應用縮放因子
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
	
	//產生並返回條碼圖像
	return generator.generateBarCodeImage();
}
```

## 實作 GetOldBarcodeImage() 方法

在此步驟中，我們將實現`getOldBarcodeImage`方法，為老式條碼產生條碼影像。在這裡，我們將處理特定的條碼類型，例如 POSTNET。這是該方法的程式碼：

```java
/// <摘要>
/// IBarCodeGenerator 介面的 GetOldBarcodeImage() 方法的實作。
/// </摘要>
/// <參數名稱=“參數”></參數>
/// <返回></返回>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	//老式條碼的硬編碼類型
	return generator.generateBarCodeImage();
}
```

## 結論

在本文中，我們探索了使用 Aspose.Words for Java 產生自訂條碼標籤的過程。我們介紹了從設定條碼高度到實現條碼產生方法的基本步驟。 Aspose.Words for Java 使開發人員能夠創建動態和自訂的條碼標籤，使其成為各個行業的寶貴工具。

## 常見問題解答

### 如何調整產生的條碼的大小？

您可以透過在提供的程式碼片段中設定條碼的符號高度和縮放係數來調整產生的條碼的大小。這些參數可讓您根據您的要求控制條碼的尺寸。

### 我可以更改條碼的顏色嗎？

是的，您可以透過在程式碼中指定前景色和背景色來變更條碼的顏色。此自訂可讓您將條碼的外觀與文件的設計相匹配。

### Aspose.Words for Java 支援哪些條碼類型？

Aspose.Words for Java 支援各種條碼類型，包括 QR 碼、CODE128、CODE39、EAN8、EAN13、UPCA、UPCE、ITF14 等。您可以選擇適合您的應用程式需求的條碼類型。

### 如何將產生的條碼整合到我的Word文件中？

若要將產生的條碼整合到 Word 文件中，您可以使用 Aspose.Words for Java 的文件操作功能。您可以將條碼影像插入文件中的所需位置。

### 是否有任何範例程式碼可用於進一步自訂？

是的，您可以在 Aspose.Words for Java 的參考網站上找到範例程式碼片段和其他文件：[Aspose.Words for Java API 參考](https://reference.aspose.com/words/java/).