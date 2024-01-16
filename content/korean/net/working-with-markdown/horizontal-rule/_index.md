---
title: 수평 법칙
linktitle: 수평 법칙
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET 단계별 가이드를 통해 수평선을 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/horizontal-rule/
---

이 예에서는 Aspose.Words for .NET에서 수평선 기능을 사용하는 방법을 보여 드리겠습니다. 수평선은 문서의 섹션을 시각적으로 구분하는 데 사용됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 수평선 삽입하기

 다음을 사용하여 수평선을 삽입할 수 있습니다.`InsertHorizontalRule` 문서 생성기의 방법.

```csharp
builder. InsertHorizontalRule();
```

## .NET용 Aspose.Words를 사용한 수평 규칙의 샘플 소스 코드

```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 수평선을 삽입합니다.
builder.InsertHorizontalRule();
```

축하합니다! 이제 Aspose.Words for .NET에서 수평선 기능을 사용하는 방법을 배웠습니다.


### FAQ

#### Q: Markdown에서 가로 눈금자를 어떻게 생성합니까?

A: Markdown에서 가로 눈금자를 만들려면 빈 줄에 다음 기호 중 하나를 사용할 수 있습니다. 별표 3개(\***), 대시 3개(\---) 또는 밑줄 3개(\___).

#### Q: Markdown에서 가로 눈금자의 모양을 사용자 지정할 수 있나요?

A: 표준 Markdown에서는 가로 눈금자의 모양을 사용자 정의할 수 있는 방법이 없습니다. 그러나 일부 고급 Markdown 편집기 및 확장은 추가 사용자 정의 기능을 제공합니다.

#### Q: 모든 Markdown 편집기에서 가로 눈금자가 지원됩니까?

A: 예, 가장 널리 사용되는 Markdown 편집기는 가로 눈금자를 지원합니다. 그러나 항상 특정 공급업체의 설명서를 확인하여 지원되는지 확인하는 것이 가장 좋습니다.

#### Q: Markdown에서 어떤 다른 요소를 만들 수 있나요?

A: 마크다운에서는 가로 눈금자 외에도 제목, 단락, 목록, 링크, 이미지, 표 등을 만들 수 있습니다.