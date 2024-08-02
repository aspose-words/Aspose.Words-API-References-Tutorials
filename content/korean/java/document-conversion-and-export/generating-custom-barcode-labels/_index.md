---
title: Aspose.Words for Java에서 사용자 정의 바코드 라벨 생성
linktitle: 맞춤형 바코드 라벨 생성
second_title: Aspose.Words Java 문서 처리 API
description: Java용 Aspose.Words에서 사용자 정의 바코드 라벨을 생성합니다. 이 단계별 가이드에서 Aspose.Words for Java를 사용하여 맞춤형 바코드 솔루션을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Aspose.Words for Java에서 사용자 정의 바코드 라벨 생성 소개

이 종합 가이드에서는 Aspose.Words for Java를 사용하여 맞춤형 바코드 라벨을 생성하는 과정을 자세히 살펴보겠습니다. Aspose.Words for Java는 개발자가 프로그래밍 방식으로 Word 문서를 조작할 수 있는 강력한 API입니다. 주목할만한 기능 중 하나는 바코드 라벨 작업 기능으로, 맞춤형 바코드 솔루션이 필요한 기업과 조직에 유용한 도구입니다.

## 전제 조건

사용자 정의 바코드 라벨 생성에 대해 자세히 알아보기 전에 전제 조건이 충족되었는지 확인하겠습니다.

1. Java 개발 환경: 시스템에 Java 및 통합 개발 환경(IDE)이 설치되어 있는지 확인하십시오.

2.  Java용 Aspose.Words: 다음에서 Java용 Aspose.Words를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/words/java/).

3. Java에 대한 기본 지식: 사용자 정의 바코드 라벨을 생성하기 위해 Java 코드를 작성하므로 Java 프로그래밍에 익숙하면 도움이 됩니다.

## 맞춤형 바코드 라벨 생성

이제 Aspose.Words for Java를 사용하여 사용자 정의 바코드 라벨을 만들어 보겠습니다. 프로세스를 여러 단계로 나누고 각 단계에 대한 Java 코드 조각을 제공하겠습니다.

## 바코드 높이 설정

시작하려면 바코드 높이를 트윕(1/1440인치) 단위로 설정해야 합니다. 그런 다음 이 값을 밀리미터(mm)로 변환합니다. 이를 수행하는 코드는 다음과 같습니다.

```java
	// 입력 값은 1/1440인치(트윕) 단위입니다.
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// mm로 변환
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## 바코드 이미지 색상 변환

다음으로 Word의 바코드 이미지 색상을 Aspose.BarCode로 변환하겠습니다. 입력 색상은 "0xRRGGBB"(16진수) 형식이어야 합니다. 변환 코드는 다음과 같습니다.

```java
/// <요약>
/// 바코드 이미지 색상을 Word에서 Aspose.BarCode로 변환합니다.
/// </summary>
/// <param name="inputColor"></param>
/// <반환></반환>
private static Color convertColor(String inputColor) throws Exception {
	// 입력은 "0x000000"에서 "0xFFFFFF" 사이여야 합니다.
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## 바코드 배율 인수 변환

이제 바코드 배율 인수를 백분율에서 부동 소수점 값으로 변환하겠습니다. 이 배율 인수는 바코드의 크기를 결정합니다. 변환 코드는 다음과 같습니다.

```java
/// <요약>
/// 바코드 배율을 백분율에서 부동 소수점으로 변환합니다.
/// </summary>
/// <param name="scalingFactor"></param>
/// <반환></반환>
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

## GetBarCodeImage() 메서드 구현

 이 단계에서는`getBarcodeImage` 제공된 매개변수를 기반으로 바코드 이미지를 생성하는 메서드입니다. 다양한 바코드 유형을 처리하고, 색상을 설정하고, 크기를 조정하는 등의 작업을 수행합니다. 이 메서드의 코드는 다음과 같습니다.

```java
/// <요약>
/// IBarCodeGenerator 인터페이스에 대한 GetBarCodeImage() 메소드 구현.
/// </summary>
/// <param name="매개변수"></param>
/// <반환></반환>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// 바코드 유형과 값이 제공되었는지 확인하세요.
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// 바코드 유형을 기반으로 BarcodeGenerator 생성
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// 여기에서 다른 바코드 유형을 처리하세요.
	}
	
	// 바코드 텍스트 설정
	generator.setCodeText(parameters.getBarcodeValue());
	
	// 바코드 색상 설정
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// 기호 높이 및 치수 설정
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//코드 텍스트 위치 사용자 정의
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// QR 코드 추가 조정
	final float SCALE = 2.4f; // Word 바코드를 Aspose.BarCode로 변환하기 위한 경험적 배율 인수
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
	
	// 배율 인수 적용
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
	
	// 바코드 이미지 생성 및 반환
	return generator.generateBarCodeImage();
}
```

## GetOldBarcodeImage() 메서드 구현

 이 단계에서는`getOldBarcodeImage` 구식 바코드에 대한 바코드 이미지를 생성하는 방법입니다. 여기서는 POSTNET과 같은 특정 바코드 유형을 처리합니다. 이 메서드의 코드는 다음과 같습니다.

```java
/// <요약>
/// IBarCodeGenerator 인터페이스에 대한 GetOldBarcodeImage() 메소드 구현.
/// </summary>
/// <param name="매개변수"></param>
/// <반환></반환>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// 구식 바코드의 하드코드 유형
	return generator.generateBarCodeImage();
}
```

## 결론

이 기사에서는 Aspose.Words for Java를 사용하여 맞춤형 바코드 라벨을 생성하는 과정을 살펴보았습니다. 바코드 높이 설정부터 바코드 생성 방법 구현까지 필수 단계를 다루었습니다. Aspose.Words for Java는 개발자가 동적 및 맞춤형 바코드 라벨을 생성할 수 있도록 지원하여 다양한 산업 분야에서 유용한 도구가 됩니다.

## FAQ

### 생성된 바코드의 크기를 어떻게 조정하나요?

제공된 코드 조각에서 바코드의 기호 높이와 배율 인수를 설정하여 생성된 바코드의 크기를 조정할 수 있습니다. 이러한 매개변수를 사용하면 요구 사항에 따라 바코드의 크기를 제어할 수 있습니다.

### 바코드 색상을 변경할 수 있나요?

예, 코드에서 전경색과 배경색을 지정하여 바코드 색상을 변경할 수 있습니다. 이 사용자 정의를 통해 바코드 모양을 문서 디자인과 일치시킬 수 있습니다.

### Aspose.Words for Java는 어떤 바코드 유형을 지원합니까?

Aspose.Words for Java는 QR 코드, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 등을 포함한 다양한 바코드 유형을 지원합니다. 귀하의 애플리케이션 요구 사항에 맞는 바코드 유형을 선택할 수 있습니다.

### 생성된 바코드를 Word 문서에 어떻게 통합하나요?

생성된 바코드를 Word 문서에 통합하려면 Aspose.Words를 사용하여 Java의 문서 조작 기능을 사용할 수 있습니다. 문서의 원하는 위치에 바코드 이미지를 삽입할 수 있습니다.

### 추가 사용자 정의에 사용할 수 있는 샘플 코드가 있습니까?

 예, Aspose.Words for Java 참조 사이트에서 샘플 코드 조각과 추가 문서를 찾을 수 있습니다.[Aspose.Words for Java API 참조](https://reference.aspose.com/words/java/).