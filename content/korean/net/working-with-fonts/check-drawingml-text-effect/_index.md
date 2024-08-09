---
title: DrawingML 텍스트 효과 확인
linktitle: DrawingML 텍스트 효과 확인
second_title: Aspose.Words 문서 처리 API
description: 자세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 DrawingML 텍스트 효과를 확인하는 방법을 알아보세요. 문서를 쉽게 향상하세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/check-drawingml-text-effect/
---
## 소개

.NET용 Aspose.Words 작업에 대한 또 다른 자세한 튜토리얼에 오신 것을 환영합니다! 오늘 우리는 DrawingML 텍스트 효과의 매혹적인 세계로 뛰어들고 있습니다. 그림자, 반사 또는 3D 효과로 Word 문서를 향상시키려는 경우 이 가이드에서는 .NET용 Aspose.Words를 사용하여 문서에서 이러한 텍스트 효과를 확인하는 방법을 보여줍니다. 시작해 봅시다!

## 전제 조건

튜토리얼을 시작하기 전에 준비해야 할 몇 가지 전제 조건이 있습니다.

-  .NET 라이브러리용 Aspose.Words: .NET 라이브러리용 Aspose.Words가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose 릴리스 페이지](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 개발 환경이 설정되어 있어야 합니다.
- C#에 대한 기본 지식: C# 프로그래밍에 어느 정도 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스를 사용하면 Word 문서를 조작하고 DrawingML 텍스트 효과를 확인하는 데 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## DrawingML 텍스트 효과 확인을 위한 단계별 가이드

이제 프로세스를 여러 단계로 나누어 더 쉽게 따라해 보겠습니다.

## 1단계: 문서 로드

첫 번째 단계는 DrawingML 텍스트 효과를 확인하려는 Word 문서를 로드하는 것입니다. 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
```

이 코드 조각은 지정된 디렉터리에서 "드로잉ML 텍스트 효과.docx"라는 문서를 로드합니다.

## 2단계: 실행 컬렉션에 액세스

다음으로 문서의 첫 번째 단락에 있는 실행 컬렉션에 액세스해야 합니다. 실행은 동일한 서식을 가진 텍스트 부분입니다.

```csharp
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
```

이 코드 줄은 문서의 첫 번째 섹션에 있는 첫 번째 단락에서 실행을 검색합니다.

## 3단계: 첫 번째 실행의 글꼴 가져오기

이제 실행 컬렉션에서 첫 번째 실행의 글꼴 속성을 가져옵니다. 이를 통해 텍스트에 적용된 다양한 DrawingML 텍스트 효과를 확인할 수 있습니다.

```csharp
Font runFont = runs[0].Font;
```

## 4단계: DrawingML 텍스트 효과 확인

마지막으로 그림자, 3D 효과, 반사, 윤곽선 및 채우기와 같은 다양한 DrawingML 텍스트 효과를 확인할 수 있습니다.

```csharp
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

 다음 코드 줄이 인쇄됩니다.`true` 또는`false` 각 특정 DrawingML 텍스트 효과가 실행 글꼴에 적용되는지 여부에 따라 달라집니다.

## 결론

축하해요! .NET용 Aspose.Words를 사용하여 Word 문서에서 DrawingML 텍스트 효과를 확인하는 방법을 배웠습니다. 이 강력한 기능을 사용하면 정교한 텍스트 서식을 프로그래밍 방식으로 감지하고 조작할 수 있어 문서 처리 작업을 더 효과적으로 제어할 수 있습니다.


## FAQ

### DrawingML 텍스트 효과란 무엇입니까?
DrawingML 텍스트 효과는 그림자, 3D 효과, 반사, 윤곽선 및 채우기를 포함하여 Word 문서의 고급 텍스트 서식 옵션입니다.

### .NET용 Aspose.Words를 사용하여 DrawingML 텍스트 효과를 적용할 수 있나요?
예, Aspose.Words for .NET을 사용하면 프로그래밍 방식으로 DrawingML 텍스트 효과를 확인하고 적용할 수 있습니다.

### .NET용 Aspose.Words를 사용하려면 라이선스가 필요합니까?
 예, .NET용 Aspose.Words는 전체 기능을 사용하려면 라이선스가 필요합니다. 당신은 얻을 수 있습니다[임시 면허증](https://purchase.aspose.com/temporary-license/) 평가를 위해.

### .NET용 Aspose.Words에 대한 무료 평가판이 있습니까?
 예, 다음을 다운로드할 수 있습니다.[무료 평가판](https://releases.aspose.com/) 구매하기 전에 Aspose.Words for .NET을 사용해 보세요.

### .NET용 Aspose.Words에 대한 추가 문서는 어디서 찾을 수 있나요?
 자세한 문서는 다음에서 찾을 수 있습니다.[.NET 문서 페이지용 Aspose.Words](https://reference.aspose.com/words/net/).