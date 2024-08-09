---
title: 특정 옵션으로 텍스트 워터마크 추가
linktitle: 특정 옵션으로 텍스트 워터마크 추가
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에 특정 옵션이 포함된 텍스트 워터마크를 추가하는 방법을 알아보세요. 글꼴, 크기, 색상, 레이아웃을 쉽게 사용자 정의하세요.
type: docs
weight: 10
url: /ko/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## 소개

워터마크는 문서를 기밀로 표시하는 것부터 개인화된 터치를 추가하는 것까지 다양한 목적으로 Word 문서에 세련되고 기능적인 추가 기능을 제공할 수 있습니다. 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 텍스트 워터마크를 추가하는 방법을 살펴보겠습니다. 글꼴 모음, 글꼴 크기, 색상, 레이아웃 등 구성할 수 있는 특정 옵션에 대해 자세히 살펴보겠습니다. 마지막에는 정확한 요구 사항에 맞게 문서의 워터마크를 사용자 정의할 수 있습니다. 이제 코드 편집기를 들고 시작해 보세요!

## 전제 조건

롤링을 시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.

1.  .NET 라이브러리용 Aspose.Words: Aspose.Words 라이브러리가 설치되어 있어야 합니다. 아직 다운로드하지 않으셨다면, 다음에서 다운로드하실 수 있습니다.[Aspose.Words 다운로드 링크](https://releases.aspose.com/words/net/).
2. C#의 기본 이해: 이 튜토리얼에서는 C#을 프로그래밍 언어로 사용합니다. C# 구문에 대한 기본적인 이해가 도움이 될 것입니다.
3. .NET 개발 환경: .NET 애플리케이션을 생성하고 실행할 수 있는 개발 환경(예: Visual Studio)이 설정되어 있는지 확인하세요.

## 네임스페이스 가져오기

Aspose.Words를 사용하려면 프로젝트에 필요한 네임스페이스를 포함해야 합니다. 가져와야 할 사항은 다음과 같습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## 1단계: 문서 설정

 먼저, 작업하려는 문서를 로드해야 합니다. 이 튜토리얼에서는 다음과 같은 샘플 문서를 사용합니다.`Document.docx`. 이 문서가 지정된 디렉터리에 있는지 확인하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 이 단계에서는 문서가 있는 디렉터리를 정의하고 이를 인스턴스에 로드합니다.`Document` 수업.

## 2단계: 워터마크 옵션 구성

다음으로 텍스트 워터마크에 대한 옵션을 구성합니다. 글꼴 모음, 글꼴 크기, 색상, 레이아웃 등 다양한 측면을 사용자 정의할 수 있습니다. 이러한 옵션을 설정해 보겠습니다.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

각 옵션의 기능은 다음과 같습니다.
- `FontFamily`: 워터마크 텍스트의 글꼴을 지정합니다.
- `FontSize`: 워터마크 텍스트의 크기를 설정합니다.
- `Color`: 워터마크 텍스트의 색상을 정의합니다.
- `Layout`워터마크의 방향(가로 또는 대각선)을 결정합니다.
- `IsSemitrasparent`: 워터마크의 반투명 여부를 설정합니다.

## 3단계: 워터마크 텍스트 추가

이제 이전에 구성한 옵션을 사용하여 문서에 워터마크를 적용합니다. 이 단계에서는 워터마크 텍스트를 "테스트"로 설정하고 정의한 옵션을 적용합니다.

```csharp
doc.Watermark.SetText("Test", options);
```

이 코드 줄은 지정된 옵션을 적용하여 "Test"라는 텍스트가 포함된 워터마크를 문서에 추가합니다.

## 4단계: 문서 저장

마지막으로 새 워터마크가 적용된 문서를 저장합니다. 원본 문서를 덮어쓰지 않도록 새 이름으로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

이 코드 조각은 수정된 문서를 새 파일 이름으로 동일한 디렉터리에 저장합니다.

## 결론

Aspose.Words for .NET을 사용하여 Word 문서에 텍스트 워터마크를 추가하는 것은 관리 가능한 단계로 분류할 때 매우 간단한 프로세스입니다. 이 튜토리얼을 따라 글꼴, 크기, 색상, 레이아웃 및 투명도를 포함한 다양한 워터마크 옵션을 구성하는 방법을 배웠습니다. 이러한 기술을 사용하면 이제 요구 사항을 더 잘 충족하거나 기밀 유지 또는 브랜딩과 같은 필수 정보를 포함하도록 문서를 사용자 정의할 수 있습니다.

 궁금한 점이 있거나 추가 도움이 필요한 경우 언제든지 다음을 확인하세요.[Aspose.Words 문서](https://reference.aspose.com/words/net/) 또는[Aspose 지원 포럼](https://forum.aspose.com/c/words/8) 더 많은 도움을 원하시면.

## FAQ

### 워터마크에 다른 글꼴을 사용할 수 있나요?

 예, 다음을 지정하여 시스템에 설치된 글꼴을 선택할 수 있습니다.`FontFamily` 에 있는 재산`TextWatermarkOptions`.

### 워터마크 색상은 어떻게 변경하나요?

 설정을 통해 워터마크의 색상을 변경할 수 있습니다.`Color` 에 있는 재산`TextWatermarkOptions` 누구에게나`System.Drawing.Color` 값.

### 문서에 여러 개의 워터마크를 추가할 수 있나요?

Aspose.Words는 한 번에 하나의 워터마크 추가를 지원합니다. 여러 개의 워터마크를 추가하려면 순차적으로 생성하고 적용해야 합니다.

### 워터마크 위치를 조정할 수 있나요?

 그만큼`WatermarkLayout`속성에 따라 방향이 결정되지만 정확한 위치 조정은 직접 지원되지 않습니다. 정확한 배치를 위해 다른 기술을 사용해야 할 수도 있습니다.

### 반투명 워터마크가 필요한 경우에는 어떻게 하나요?

 설정`IsSemitrasparent`재산`true` 워터마크를 반투명하게 만들려면