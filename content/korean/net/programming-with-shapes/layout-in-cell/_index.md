---
title: 셀의 레이아웃
linktitle: 셀의 레이아웃
second_title: Aspose.Words 문서 처리 API
description: 이 포괄적인 가이드를 통해 .NET용 Aspose.Words를 사용하여 셀에서 레이아웃을 설정하는 방법을 알아보세요. Word 문서를 사용자 정의하려는 개발자에게 적합합니다.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/layout-in-cell/
---
## 소개

Word 문서에서 표 셀의 레이아웃을 프로그래밍 방식으로 미세 조정하고 싶다면 올바른 위치에 오셨습니다. 오늘은 Aspose.Words for .NET을 사용하여 셀에 레이아웃을 설정하는 방법에 대해 알아 보겠습니다. 실제 예제를 단계별로 나누어서 쉽게 따라할 수 있도록 하겠습니다.

## 전제 조건

코드를 시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

1.  .NET용 Aspose.Words: .NET용 Aspose.Words 라이브러리가 설치되어 있는지 확인하세요. 아직 안 해보셨다면 할 수 있습니다[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
2. 개발 환경: .NET으로 설정된 개발 환경이 필요합니다. 권장 사항을 찾고 있다면 Visual Studio가 탁월한 선택입니다.
3. C#에 대한 기본 지식: 각 단계를 설명하지만 C#에 대한 기본 지식을 이해하면 더 쉽게 따라갈 수 있습니다.
4.  문서 디렉터리: 문서를 저장할 디렉터리 경로를 준비합니다. 우리는 이것을 다음과 같이 지칭할 것이다.`YOUR DOCUMENT DIRECTORY`.

## 네임스페이스 가져오기

시작하려면 프로젝트에서 필요한 네임스페이스를 가져오고 있는지 확인하세요.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

프로세스를 관리 가능한 단계로 나누어 보겠습니다.

## 1단계: 새 문서 만들기

 먼저 새 Word 문서를 만들고`DocumentBuilder` 콘텐츠를 구성하는 데 도움이 되는 개체입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 테이블 시작 및 행 형식 설정

테이블 구성을 시작하고 행의 높이 및 높이 규칙을 지정하겠습니다.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## 3단계: 셀 삽입 및 콘텐츠 채우기

다음으로, 테이블에 셀을 삽입하기 위해 반복합니다. 7개의 셀마다 행을 종료하여 새 셀을 만듭니다.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## 4단계: 워터마크 모양 추가

 이제 문서에 워터마크를 추가해 보겠습니다. 우리는`Shape` 개체를 선택하고 해당 속성을 설정합니다.

```csharp
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
```

## 5단계: 워터마크 모양 사용자 정의

색상 및 텍스트 속성을 설정하여 워터마크의 모양을 추가로 사용자 정의하겠습니다.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## 6단계: 문서에 워터마크 삽입

문서에서 마지막 실행을 찾아 해당 위치에 워터마크를 삽입합니다.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## 7단계: Word 2010에 맞게 문서 최적화

호환성을 보장하기 위해 Word 2010에 맞게 문서를 최적화하겠습니다.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## 8단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## 결론

그리고 거기에 있습니다! 사용자 정의된 테이블 레이아웃으로 Word 문서를 성공적으로 만들고 Aspose.Words for .NET을 사용하여 워터마크를 추가했습니다. 이 튜토리얼의 목적은 프로세스의 각 부분을 이해하는 데 도움이 되는 명확한 단계별 가이드를 제공하는 것입니다. 이러한 기술을 사용하면 이제 프로그래밍 방식으로 더욱 정교하고 사용자 정의된 Word 문서를 만들 수 있습니다.

## FAQ

### 워터마크 텍스트에 다른 글꼴을 사용할 수 있나요?
 예, 설정을 통해 글꼴을 변경할 수 있습니다.`watermark.TextPath.FontFamily` 속성을 원하는 글꼴로 설정하세요.

### 워터마크 위치는 어떻게 조정하나요?
 다음을 수정할 수 있습니다.`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , 그리고`VerticalAlignment` 워터마크 위치를 조정하는 속성입니다.

### 워터마크에 텍스트 대신 이미지를 사용할 수 있나요?
 전적으로! 당신은 만들 수 있습니다`Shape` 유형과 함께`ShapeType.Image` 다음을 사용하여 이미지를 설정합니다.`ImageData.SetImage` 방법.

### 행 높이가 다양한 테이블을 만들 수 있나요?
예, 다음을 변경하여 각 행의 높이를 다르게 설정할 수 있습니다.`RowFormat.Height` 해당 행에 셀을 삽입하기 전에 속성을 사용하세요.

### 문서에서 워터마크를 어떻게 제거하나요?
 문서의 모양 컬렉션에서 워터마크를 찾고`Remove` 방법.