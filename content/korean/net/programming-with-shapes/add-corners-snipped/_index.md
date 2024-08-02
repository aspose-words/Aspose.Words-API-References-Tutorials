---
title: 잘린 모서리 추가
linktitle: 잘린 모서리 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 모서리 잘린 모양을 추가하는 방법을 알아보세요. 이 단계별 가이드를 통해 문서를 쉽게 향상할 수 있습니다.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/add-corners-snipped/
---
## 소개

Word 문서에 사용자 지정 도형을 추가하면 중요한 정보를 강조하거나 콘텐츠에 약간의 세련미를 더할 수 있는 재미있고 시각적으로 매력적인 방법이 될 수 있습니다. 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 "모퉁이 잘린" 모양을 Word 문서에 삽입하는 방법을 살펴보겠습니다. 이 가이드는 모든 단계를 안내하여 이러한 도형을 쉽게 추가하고 전문가처럼 문서를 사용자 지정할 수 있도록 도와줍니다.

## 전제 조건

코드를 시작하기 전에 시작하는 데 필요한 모든 것이 갖추어져 있는지 확인하겠습니다.

1.  .NET용 Aspose.Words: 아직 다운로드하지 않았다면 다음 사이트에서 최신 버전을 다운로드하세요.[Aspose 릴리스 페이지](https://releases.aspose.com/words/net/).
2. 개발 환경: 개발 환경을 설정합니다. Visual Studio가 널리 사용되지만 .NET을 지원하는 모든 IDE를 사용할 수 있습니다.
3.  라이센스: 단지 실험 중이라면 다음을 사용할 수 있습니다.[무료 시험판](https://releases.aspose.com/) 아니면[임시 면허증](https://purchase.aspose.com/temporary-license/) 전체 기능의 잠금을 해제합니다.
4. C#에 대한 기본 이해: C# 프로그래밍에 익숙하면 예제를 따라가는 데 도움이 됩니다.

## 네임스페이스 가져오기

.NET용 Aspose.Words 작업을 시작하기 전에 필요한 네임스페이스를 가져와야 합니다. C# 파일 상단에 다음을 추가하세요.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

이제 "모서리 잘림" 모양을 추가하는 과정을 여러 단계로 나누어 보겠습니다. 모든 것이 원활하게 작동하도록 하려면 다음 단계를 자세히 따르십시오.

## 1단계: 문서 및 DocumentBuilder 초기화

 가장 먼저 해야 할 일은 새 문서를 만들고 초기화하는 것입니다.`DocumentBuilder` 물체. 이 빌더는 문서에 콘텐츠를 추가하는 데 도움이 됩니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 이 단계에서는 문서와 빌더를 설정했습니다. 생각해보세요`DocumentBuilder` 디지털 펜으로 Word 문서에 쓰고 그릴 수 있습니다.

## 2단계: 모서리 잘린 모양 삽입

 다음으로 우리는`DocumentBuilder` "모서리 잘림" 모양을 삽입합니다. 이 모양 유형은 Aspose.Words에 미리 정의되어 있으며 한 줄의 코드로 쉽게 삽입할 수 있습니다.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

여기서는 모양 유형과 크기(50x50)를 지정합니다. 문서에 작고 완벽하게 잘라진 모서리 스티커를 붙이고 있다고 상상해 보십시오. 

## 3단계: 규정 준수를 통해 저장 옵션 정의

문서를 저장하기 전에 문서가 특정 표준을 준수하도록 저장 옵션을 정의해야 합니다. 우리는`OoxmlSaveOptions` 이에 대한 수업입니다.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
```

이러한 저장 옵션은 우리 문서가 ISO/IEC 29500:2008 표준을 준수하도록 보장하며, 이는 호환성과 문서 수명에 매우 중요합니다.

## 4단계: 문서 저장

마지막으로 앞서 정의한 저장 옵션을 사용하여 문서를 지정된 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

마찬가지로 이제 문서에는 필요한 규정 준수 옵션과 함께 저장된 사용자 정의 "모서리 잘림" 모양이 포함됩니다.

## 결론

거기 있어요! Aspose.Words for .NET을 사용하여 Word 문서에 사용자 정의 모양을 추가하는 것은 간단하며 문서의 시각적 매력을 크게 향상시킬 수 있습니다. 다음 단계를 따르면 "모서리 잘림" 모양을 쉽게 삽입하고 문서가 필수 표준을 충족하는지 확인할 수 있습니다. 즐거운 코딩하세요!

## FAQ

### "모서리 잘림" 모양의 크기를 사용자 정의할 수 있나요?
예, 크기를 변경하여 크기를 조정할 수 있습니다.`InsertShape` 방법.

### 다른 유형의 도형을 추가할 수 있나요?
 전적으로! Aspose.Words는 다양한 모양을 지원합니다. 그냥 바꾸세요`ShapeType` 원하는 모양으로.

### Aspose.Words를 사용하려면 라이센스가 필요합니까?
무료 평가판이나 임시 라이센스를 사용할 수 있지만 제한 없이 사용하려면 정식 라이센스가 필요합니다.

### 도형의 스타일을 추가로 지정하려면 어떻게 해야 합니까?
Aspose.Words에서 제공하는 추가 속성과 메서드를 사용하여 모양의 모양과 동작을 사용자 지정할 수 있습니다.

### Aspose.Words는 다른 형식과 호환됩니까?
예, Aspose.Words는 DOCX, PDF, HTML 등을 포함한 다양한 문서 형식을 지원합니다.