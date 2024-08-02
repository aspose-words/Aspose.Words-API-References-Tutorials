---
title: 그룹 모양 추가
linktitle: 그룹 모양 추가
second_title: Aspose.Words 문서 처리 API
description: 이 포괄적인 단계별 튜토리얼을 통해 .NET용 Aspose.Words를 사용하여 Word 문서에 그룹 모양을 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/add-group-shape/
---
## 소개

풍부한 시각적 요소가 포함된 복잡한 문서를 만드는 것은 때로 어려운 작업이 될 수 있으며, 특히 그룹 모양을 처리할 때 더욱 그렇습니다. 하지만 두려워하지 마세요! .NET용 Aspose.Words는 이 프로세스를 단순화하여 파이처럼 쉽게 만듭니다. 이 자습서에서는 Word 문서에 그룹 도형을 추가하는 단계를 안내합니다. 다이빙할 준비가 되셨나요? 시작하자!

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1.  .NET용 Aspose.Words: 다음에서 다운로드할 수 있습니다.[Aspose 릴리스 페이지](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio 또는 .NET과 호환되는 기타 IDE.
3. C#에 대한 기본 이해: C# 프로그래밍에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

시작하려면 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 Aspose.Words를 사용하여 Word 문서를 조작하는 데 필요한 클래스 및 메서드에 대한 액세스를 제공합니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 1단계: 문서 초기화

먼저 새 Word 문서를 초기화해 보겠습니다. 이를 그룹 모양을 추가할 빈 캔버스를 만드는 것으로 생각하십시오.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 여기,`EnsureMinimum()` 문서에 필요한 최소한의 노드 세트를 추가합니다.

## 2단계: GroupShape 개체 만들기

 다음으로`GroupShape`물체. 이 개체는 다른 모양에 대한 컨테이너 역할을 하여 그룹화할 수 있습니다.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## 3단계: GroupShape에 도형 추가

 이제 개별 모양을`GroupShape` 컨테이너. 강조 테두리 모양으로 시작한 다음 작업 버튼 모양을 추가하겠습니다.

### 악센트 테두리 모양 추가

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 이 코드 조각은 너비와 높이가 100단위인 악센트 테두리 모양을 생성하고`GroupShape`.

### 액션 버튼 모양 추가하기

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 여기서는 작업 버튼 모양을 만들고 위치를 지정한 다음`GroupShape`.

## 4단계: GroupShape 치수 정의

 모양이 그룹 내에 잘 들어맞도록 하려면 크기를 설정해야 합니다.`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 이는 너비와 높이를 정의합니다.`GroupShape` 200 단위로 지정하고 이에 따라 좌표 크기를 설정합니다.

## 5단계: 문서에 GroupShape 삽입

 이제`GroupShape` 사용하여 문서에`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` 도형을 포함한 노드를 문서에 추가하는 쉬운 방법을 제공합니다.

## 6단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

그리고 거기에 있습니다! 그룹 도형이 포함된 문서가 준비되었습니다.

## 결론

Word 문서에 그룹 셰이프를 추가하는 과정은 복잡할 필요가 없습니다. Aspose.Words for .NET을 사용하면 모양을 쉽게 만들고 조작하여 문서를 시각적으로 더욱 매력적이고 기능적으로 만들 수 있습니다. 이 튜토리얼에 설명된 단계를 따르면 곧 전문가가 될 것입니다!

## FAQ

### GroupShape에 두 개 이상의 도형을 추가할 수 있나요?
 예, 필요한 만큼 많은 도형을 추가할 수 있습니다.`GroupShape` . 그냥 사용`AppendChild` 각 모양별 방법입니다.

### GroupShape 내에서 도형의 스타일을 지정할 수 있습니까?
 전적으로! 각 모양은 다음에서 사용 가능한 속성을 사용하여 개별적으로 스타일을 지정할 수 있습니다.`Shape` 수업.

### 문서 내에서 GroupShape를 어떻게 배치합니까?
 위치를 지정할 수 있습니다.`GroupShape` 설정하여`Left`그리고`Top` 속성.

### GroupShape 내의 도형에 텍스트를 추가할 수 있나요?
 예, 다음을 사용하여 도형에 텍스트를 추가할 수 있습니다.`AppendChild` 추가하는 방법`Paragraph` 포함하는`Run` 텍스트가 있는 노드.

### 사용자 입력에 따라 도형을 동적으로 그룹화할 수 있습니까?
예, 그에 따라 속성과 메서드를 조정하여 사용자 입력을 기반으로 도형을 동적으로 만들고 그룹화할 수 있습니다.