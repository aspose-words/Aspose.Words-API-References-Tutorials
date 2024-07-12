---
title: 셀의 레이아웃
linktitle: 셀의 레이아웃
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 표 셀 내에서 모양을 레이아웃하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/layout-in-cell/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 표 셀 내에 모양을 레이아웃하는 방법을 설명합니다. 모양 속성을 조정하고 레이아웃 옵션을 사용하여 셀 내 모양의 위치와 모양을 제어할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"`문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 문서 및 DocumentBuilder 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 문서 작업에 사용할 개체입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 테이블 구축
 사용`StartTable`, `EndTable`, `InsertCell` , 그리고`Write` 방법`DocumentBuilder`테이블을 만드는 개체입니다. 다음을 사용하여 원하는 행 높이 및 높이 규칙을 설정합니다.`RowFormat` 속성.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## 4단계: 도형 만들기 및 서식 지정
 만들기`Shape` 개체를 선택하고 해당 속성을 구성하여 워터마크를 정의합니다. 다음을 사용하여 셀 내에 배치할 모양을 설정합니다.`IsLayoutInCell` 재산.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## 5단계: 모양 사용자 정의
 다음과 같은 속성을 설정하여 워터마크 모양의 모양과 텍스트를 사용자 정의합니다.`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`, 등.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## 6단계: 문서에 도형 삽입
 다음을 사용하여 워터마크 모양을 문서에 삽입합니다.`InsertNode` 의 방법`DocumentBuilder` 물체. 다음을 사용하여 모양의 위치를 지정합니다.`MoveTo` 문서에서 마지막 실행 이후에 배치하는 방법입니다.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## 7단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithShapes.LayoutInCell.docx"로 저장합니다.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### .NET용 Aspose.Words를 사용하는 Layout In Cell의 소스 코드 예 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // 셀에 배치할 경우 표 셀 외부에 모양을 표시합니다.
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서의 표 셀 내에 모양을 성공적으로 배치했습니다.