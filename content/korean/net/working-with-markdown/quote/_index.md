---
title: 인용하다
linktitle: 인용하다
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 견적을 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/quote/
---

이 예에서는 Aspose.Words for .NET 견적에서 인용 기능을 사용하는 방법을 설명합니다. 인용은 텍스트 섹션을 특수 테두리로 둘러싸서 강조 표시하는 데 사용됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 기본 인용 스타일 사용

텍스트에 인용 서식을 적용하기 위해 "인용"이라는 기본 단락 스타일을 사용하겠습니다.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## 3단계: 중첩된 수준에 대한 스타일 만들기

 다음을 사용하여 중첩된 수준에 대한 스타일을 만들 수 있습니다.`Styles.Add` 의 방법`Document` 물체. 이 예에서는 중첩된 인용 수준을 나타내기 위해 "Quote1"이라는 스타일을 만듭니다.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### .NET용 Aspose.Words 인용을 위한 예제 소스 코드


```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 기본적으로 문서는 첫 번째 수준의 인용부호 스타일을 저장합니다.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// 스타일 상속을 통해 중첩된 수준에 대한 스타일을 만듭니다.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

축하합니다! 이제 Aspose.Words for .NET에서 인용 기능을 사용하는 방법을 배웠습니다.


### FAQ

#### Q: 마크다운에서 인용이란 무엇인가요?

A: Markdown의 인용문은 다른 소스의 텍스트 구절을 강조 표시하거나 유명한 인용문을 참조하는 방법입니다.

#### Q: 마크다운에서 따옴표를 어떻게 사용하나요?

A: Markdown에서 인용문을 사용하려면 인용문 텍스트를 꺾쇠괄호(`>`). 인용의 각 줄은 갈매기형 문자로 시작해야 합니다.

#### Q: Markdown 인용문은 속성을 지원합니까?

A: 마크다운 인용은 특정 속성을 지원하지 않습니다. 인용된 텍스트의 형식으로 강조 표시됩니다.

#### Q: Markdown에 따옴표를 삽입할 수 있나요?

A: 예, 추가 수준의 꺾쇠 괄호(`>`).