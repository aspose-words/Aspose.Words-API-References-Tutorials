---
title: 수직 앵커
linktitle: 수직 앵커
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 텍스트 상자의 수직 앵커 위치를 설정하는 방법을 알아보세요. 쉬운 단계별 가이드가 포함되어 있습니다.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/vertical-anchor/
---
## 소개

Word 문서의 텍스트 상자 안에 텍스트가 표시되는 위치를 정확하게 제어해야 하는 경우가 있습니까? 텍스트를 텍스트 상자의 상단, 중간 또는 하단에 고정하고 싶습니까? 그렇다면, 당신은 바로 이곳에 있습니다! 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 텍스트 상자의 수직 앵커를 설정하는 방법을 살펴보겠습니다. 컨테이너 내에서 원하는 위치에 텍스트를 정확하게 배치하는 마술 지팡이로 수직 앵커링을 생각해 보세요. 다이빙할 준비가 되셨나요? 시작하자!

## 전제 조건

수직 앵커링의 기본 사항에 대해 자세히 알아보기 전에 몇 가지 사항을 준비해야 합니다.

1.  .NET용 Aspose.Words: .NET용 Aspose.Words 라이브러리가 설치되어 있는지 확인하세요. 아직 갖고 있지 않다면 다음을 수행할 수 있습니다.[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
2. Visual Studio: 이 튜토리얼에서는 코딩을 위해 Visual Studio 또는 다른 .NET IDE를 사용하고 있다고 가정합니다.
3. C#에 대한 기본 지식: C# 및 .NET에 익숙하면 원활하게 작업을 진행하는 데 도움이 됩니다.

## 네임스페이스 가져오기

시작하려면 C# 코드에서 필요한 네임스페이스를 가져와야 합니다. 여기에서 사용할 클래스와 메서드를 찾을 수 있는 위치를 애플리케이션에 알려줍니다. 수행 방법은 다음과 같습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

이러한 네임스페이스는 문서 및 셰이프 작업에 필요한 클래스를 제공합니다.

## 1단계: 문서 초기화

먼저 새 Word 문서를 만들어야 합니다. 페인팅을 시작하기 전에 캔버스를 설정하는 것으로 생각하십시오.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 여기,`Document` 당신의 빈 캔버스이고`DocumentBuilder` 도형과 텍스트를 추가할 수 있는 그림붓입니다.

## 2단계: TextBox 도형 삽입

이제 문서에 텍스트 상자를 추가해 보겠습니다. 여기에 텍스트가 표시됩니다. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 이 예에서는`ShapeType.TextBox` 원하는 모양을 지정하고`200, 200` 텍스트 상자의 너비와 높이(포인트)입니다.

## 3단계: 수직 앵커 설정

마법이 일어나는 곳은 바로 여기입니다! 텍스트 상자 내 텍스트의 수직 정렬을 설정할 수 있습니다. 이는 텍스트가 텍스트 상자의 상단, 중간 또는 하단에 고정되는지 여부를 결정합니다.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 이 경우,`TextBoxAnchor.Bottom`텍스트가 텍스트 상자 하단에 고정되도록 합니다. 중앙에 정렬하거나 상단에 정렬하려면 다음을 사용하십시오.`TextBoxAnchor.Center` 또는`TextBoxAnchor.Top`, 각각.

## 4단계: TextBox에 텍스트 추가

이제 텍스트 상자에 일부 내용을 추가할 차례입니다. 마지막 손질로 캔버스를 채우는 것이라고 생각하세요.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 여기,`MoveTo` 텍스트가 텍스트 상자에 삽입되었는지 확인하고`Write` 실제 텍스트를 추가합니다.

## 5단계: 문서 저장

마지막 단계는 문서를 저장하는 것입니다. 이는 마치 완성된 그림을 액자에 넣는 것과 같습니다.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서의 텍스트 상자 내에서 텍스트의 수직 정렬을 제어하는 방법을 배웠습니다. 텍스트를 상단, 중앙, 하단에 고정하는 경우 이 기능을 사용하면 문서 레이아웃을 정밀하게 제어할 수 있습니다. 따라서 다음에 문서의 텍스트 배치를 조정해야 할 때 무엇을 해야 할지 알게 될 것입니다!

## FAQ

### Word 문서에서 수직 고정이란 무엇입니까?
수직 고정은 위쪽, 중간, 아래쪽 정렬 등 텍스트 상자 내에서 텍스트가 배치되는 위치를 제어합니다.

### 텍스트 상자 외에 다른 모양을 사용할 수 있나요?
예, 다른 모양에도 수직 고정을 사용할 수 있습니다. 하지만 텍스트 상자가 가장 일반적인 사용 사례입니다.

### 텍스트 상자를 만든 후 기준점을 어떻게 변경합니까?
 앵커 포인트를 설정하여 변경할 수 있습니다.`VerticalAnchor` 텍스트 상자 모양 개체의 속성입니다.

### 텍스트 상자 중앙에 텍스트를 고정할 수 있나요?
 전적으로! 그냥 사용`TextBoxAnchor.Center` 텍스트 상자 내에서 텍스트를 세로로 가운데에 배치합니다.

### .NET용 Aspose.Words에 대한 자세한 정보는 어디서 찾을 수 있나요?
 확인해 보세요[Aspose.Words 문서](https://reference.aspose.com/words/net/) 자세한 내용과 가이드를 확인하세요.