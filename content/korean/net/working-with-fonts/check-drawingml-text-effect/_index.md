---
title: DrawingML 텍스트 효과 확인
linktitle: DrawingML 텍스트 효과 확인
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 DrawingML 텍스트 효과를 확인하는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/check-drawingml-text-effect/
---

이 튜토리얼에서는 .NET용 Aspose.Words Library를 사용하여 Word 문서에서 DrawingML 텍스트 효과를 확인하는 방법을 안내합니다. DrawingML 텍스트 효과를 확인하면 특정 효과가 텍스트 일부에 적용되는지 확인할 수 있습니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

## 전제 조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리
- DrawingML 텍스트 효과가 포함된 Word 문서

## 1단계: 문서 디렉터리 정의
 먼저, Word 문서 위치에 대한 디렉터리 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서를 로드하고 텍스트 효과 확인
다음으로 Word 문서를 로드하고 문서 본문의 첫 번째 단락에 있는 실행 모음(문자 시퀀스)에 액세스합니다. 다음으로 첫 번째 실행 글꼴에 특정 DrawingML 텍스트 효과가 적용되었는지 확인하겠습니다.

```csharp
// 문서를 로드하세요
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// DrawingML 텍스트 효과 확인
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### .NET용 Aspose.Words를 사용하여 DMLText 효과 확인을 위한 샘플 소스 코드 

```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// 한 번의 실행으로 여러 Dml 텍스트 효과가 적용될 수 있습니다.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 DrawingML 텍스트 효과를 확인하는 방법을 살펴보았습니다. DrawingML 텍스트 효과를 확인하면 특정 효과가 적용된 텍스트 부분을 식별할 수 있습니다. 이 기능을 사용하여 Word 문서에서 텍스트 효과를 조작하고 분석할 수 있습니다.

### FAQ

#### Q: Aspose.Words를 사용하여 Word 문서에서 DrawingML 텍스트 효과에 어떻게 액세스할 수 있나요?

A: Aspose.Words를 사용하면 제공된 API를 사용하여 Word 문서에서 DrawingML 텍스트 효과에 액세스할 수 있습니다. 텍스트 요소를 탐색하고 색상, 크기 등과 같은 텍스트 효과의 특정 속성을 확인할 수 있습니다.

#### Q: Word 문서에 일반적으로 사용되는 DrawingML 텍스트 효과 유형은 무엇입니까?

A: Word 문서에서 일반적으로 사용되는 DrawingML 텍스트 효과 유형에는 그림자, 반사, 광선, 그라데이션 등이 포함됩니다. 이러한 효과를 적용하여 텍스트의 모양과 서식을 개선할 수 있습니다.

#### Q: Word 문서에서 DrawingML 텍스트 효과의 색상을 어떻게 확인할 수 있나요?

A: Word 문서에서 DrawingML 텍스트 효과의 색상을 확인하려면 Aspose.Words에서 제공하는 메서드를 사용하여 텍스트 효과의 색상 속성에 액세스할 수 있습니다. 이렇게 하면 특정 텍스트 효과에 사용되는 색상을 얻을 수 있습니다.

#### Q: 여러 섹션이 포함된 Word 문서에서 텍스트 효과를 확인할 수 있나요?

A: 예, Aspose.Words를 사용하면 여러 섹션이 포함된 Word 문서에서 텍스트 효과를 확인할 수 있습니다. 문서의 각 섹션을 탐색하고 각 섹션의 텍스트 효과에 개별적으로 액세스할 수 있습니다.

#### Q: Word 문서에서 DrawingML 텍스트 효과의 불투명도를 어떻게 확인할 수 있나요?

A: Word 문서에서 DrawingML 텍스트 효과의 불투명도를 확인하려면 Aspose.Words에서 제공하는 메서드를 사용하여 텍스트 효과의 불투명도 속성에 액세스할 수 있습니다. 이를 통해 특정 텍스트 효과에 불투명도 값을 적용할 수 있습니다.