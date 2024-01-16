---
title: 펜스된 코드
linktitle: 펜스된 코드
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드로 분리 코드 기능을 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/fenced-code/
---

이 예에서는 Aspose.Words for .NET에서 분리 코드 기능을 사용하는 방법을 안내합니다. 울타리 코드는 특정 형식의 코드 블록을 나타내는 데 사용됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 분리된 코드에 대한 스타일 추가

 다음을 사용하여 울타리 코드에 대한 사용자 정의 스타일을 추가하겠습니다.`Styles.Add` 의 방법`Document` 물체. 이 예에서는 분리된 코드에 대해 "FencedCode"라는 스타일을 생성합니다.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## 3단계: 정보 없이 분리된 코드 추가

이제 "FencedCode" 사용자 정의 스타일을 사용하여 정보 문자열이 없는 울타리 코드 블록을 추가할 수 있습니다.

```csharp
builder.Writeln("This is an fenced code");
```

## 4단계: 정보 문자열이 포함된 분리 코드 추가

다른 사용자 정의 스타일을 사용하여 정보 문자열이 포함된 분리된 코드 블록을 추가할 수도 있습니다. 이 예에서는 C# 코드 블록을 나타내기 위해 "FencedCode.C#"이라는 스타일을 만듭니다.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### .NET용 Aspose.Words를 사용하는 Fenced Code의 예제 소스 코드

```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### FAQ

#### Q: Markdown의 구분 코드란 무엇입니까?

A: Markdown의 구분 코드는 Markdown 문서에 코드를 표시하는 데 사용되는 서식 지정 방법입니다. 이는 특정 구분 기호를 사용하여 코드를 프레이밍하는 것으로 구성됩니다.

#### Q: Markdown에서 구분 코드를 사용하면 어떤 이점이 있나요?

A: Markdown의 구분 코드는 코드 가독성을 높이고 독자가 더 쉽게 이해할 수 있도록 해줍니다. 또한 일부 Markdown 편집기에서 구문 강조를 유지할 수 있습니다.

#### Q: Markdown에서 구분된 코드와 들여쓰기된 코드의 차이점은 무엇입니까?

A: 구분 코드는 특정 구분 기호를 사용하여 코드를 묶는 반면, 들여쓰기 코드는 각 코드 줄을 공백이나 탭으로 들여쓰기합니다.

#### Q: 모든 Markdown 편집기에서 Markdown의 구분 코드를 지원합니까?

A: Markdown의 구분 코드 지원은 Markdown 편집기마다 다를 수 있습니다. 확실하게 알아보려면 게시자의 특정 설명서를 확인하세요.

