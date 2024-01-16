---
title: 특정 옵션으로 텍스트 워터마크 추가
linktitle: 특정 옵션으로 텍스트 워터마크 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 특정 옵션으로 텍스트 워터마크를 추가하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 10
url: /ko/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 특정 옵션으로 텍스트 워터마크를 추가하는 방법을 안내합니다. 텍스트 워터마크는 초안, 기밀 등을 나타내기 위해 문서에 겹쳐진 텍스트입니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드

문서 경로를 사용하여 기존 문서를 로드합니다.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 3단계: 특정 옵션으로 텍스트 워터마크 추가

 우리는`TextWatermarkOptions` 클래스를 선택하고 텍스트 워터마크에 대해 원하는 옵션을 설정합니다.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## 4단계: 문서 저장

마지막으로 텍스트 워터마크가 추가된 문서를 저장할 수 있습니다.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### .NET용 Aspose.Words를 사용하여 특정 옵션으로 텍스트 워터마크를 추가하는 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 특정 옵션으로 텍스트 워터마크를 추가하는 방법을 배웠습니다.

