---
title: Word 문서의 단락에 테두리 및 음영 적용
linktitle: Word 문서의 단락에 테두리 및 음영 적용
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서의 단락에 테두리와 음영을 적용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
이 튜토리얼에서는 .NET용 Aspose.Words의 기능을 사용하여 Word 문서의 단락에 테두리와 음영을 적용하는 방법을 보여 드리겠습니다. 소스 코드를 이해하고 서식 변경 사항을 적용하려면 아래 단계를 따르세요.

## 1단계: 문서 만들기 및 구성

시작하려면 새 문서와 관련 DocumentBuilder 개체를 만듭니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 테두리 구성

이제 각 측면의 테두리 스타일을 지정하여 단락 테두리를 구성해 보겠습니다. 방법은 다음과 같습니다.

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## 3단계: 채우기 설정

이제 텍스처와 채우기 색상을 지정하여 단락 채우기를 구성하겠습니다. 방법은 다음과 같습니다.

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## 4단계: 콘텐츠 추가

단락에 일부 형식화된 콘텐츠를 추가하겠습니다. 방법은 다음과 같습니다.

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## 3단계: 문서 저장

 텍스트 입력 양식 필드를 삽입한 후,`Save` 방법. 적절한 파일 경로를 제공해야 합니다.

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### .NET용 Aspose.Words를 사용하여 단락에 테두리 및 음영 적용에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 단락에 테두리 및 음영 적용 기능에 대한 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## 결론

 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 단락에 테두리와 음영을 적용하는 방법을 배웠습니다. 단락을 구성하여`Borders` 그리고`Shading` 속성을 사용하여 단락의 테두리 스타일, 선 색상 및 채우기 색상을 설정할 수 있었습니다. Aspose.Words for .NET은 단락의 모양을 사용자 정의하고 문서의 시각적 표현을 향상시키는 강력한 서식 기능을 제공합니다.

### FAQ

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서의 단락에 테두리와 음영을 어떻게 적용합니까?

A: .NET용 Aspose.Words를 사용하여 Word 문서의 단락에 테두리와 음영을 적용하려면 다음 단계를 따르세요.
1.  새 문서를 만들고`DocumentBuilder` 물체.
2.  액세스하여 단락 테두리를 구성합니다.`Borders` 의 재산`ParagraphFormat` 각 측면의 테두리 스타일을 설정합니다.
3. 액세스하여 단락 채우기를 구성합니다.`Shading` 의 재산`ParagraphFormat` 텍스처와 채우기 색상을 지정합니다.
4.  다음을 사용하여 단락에 내용을 추가합니다.`Write` 의 방법`DocumentBuilder`.
5.  다음을 사용하여 문서를 저장합니다.`Save` 방법.

#### Q: 단락의 각 측면에 대한 테두리 스타일을 어떻게 설정합니까?

 A: 단락의 각 측면에 테두리 스타일을 설정하려면`Borders` 의 재산`ParagraphFormat` 그리고 설정`LineStyle` 각각의 재산`BorderType` (예:`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). 다음과 같은 다양한 선 스타일을 지정할 수 있습니다.`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, 등.

#### Q: 단락 음영의 질감과 채우기 색상을 어떻게 지정합니까?

 A: 단락 음영의 질감과 채우기 색상을 지정하려면`Shading` 의 재산`ParagraphFormat` 그리고 설정`Texture` 원하는 텍스처 인덱스에 대한 속성(예:`TextureIndex.TextureDiagonalCross` ). 다음을 설정할 수도 있습니다.`BackgroundPatternColor` 그리고`ForegroundPatternColor` 속성을 사용하여 원하는 색상으로`System.Drawing.Color` 수업.