---
title: 들여쓰기된 코드
linktitle: 들여쓰기된 코드
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET 단계별 가이드를 통해 들여쓰기된 코드를 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/indented-code/
---

이 예에서는 Aspose.Words for .NET에서 들여쓰기된 코드 기능을 사용하는 방법을 설명합니다. 들여쓰기된 코드는 특정 형식의 코드 블록을 시각적으로 나타내는 데 사용됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 들여쓰기된 코드에 스타일 추가

 다음을 사용하여 들여쓰기된 코드에 대한 사용자 정의 스타일을 추가하겠습니다.`Styles.Add` 의 방법`Document` 물체. 이 예에서는 들여쓰기된 코드에 대해 "IndentedCode"라는 스타일을 만듭니다.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## 3단계: 들여쓰기된 코드 추가

이제 "IndentedCode" 사용자 정의 스타일을 사용하여 들여쓰기된 코드 블록을 추가할 수 있습니다.

```csharp
builder.Writeln("This is an indented code block");
```

### .NET용 Aspose.Words를 사용한 들여쓰기된 코드의 예제 소스 코드

```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

축하합니다! 이제 Aspose.Words for .NET에서 들여쓰기된 코드 기능을 사용하는 방법을 배웠습니다.


### FAQ

#### Q: Markdown에서 들여쓰기된 코드란 무엇입니까?

A: Markdown의 들여쓰기 코드는 Markdown 문서에 코드를 표시하는 데 사용되는 서식 지정 방법입니다. 공백이나 탭을 사용하여 각 코드 줄을 들여쓰기하는 것으로 구성됩니다.

#### Q: 마크다운에서 들여쓰기된 코드를 어떻게 사용하나요?

A: Markdown에서 들여쓰기된 코드를 사용하려면 공백이나 탭을 사용하여 각 코드 줄을 들여쓰기하세요.

#### Q: Markdown에서 들여쓰기된 코드의 장점은 무엇입니까?

A: Markdown의 들여쓰기된 코드는 코드 가독성을 높이고 독자가 이해하기 쉽게 만듭니다.

#### Q: 마크다운에서 들여쓰기된 코드와 코드 블록의 차이점은 무엇입니까?

A: 들여쓰기된 코드는 텍스트에 삽입되는 작은 코드 조각에 사용되는 반면, 코드 블록은 별도의 서식으로 더 큰 코드 조각을 표시하는 데 사용됩니다.

#### Q: 모든 Markdown 편집기에서 Markdown의 들여쓰기된 코드를 지원합니까?

A: Markdown에서 들여쓰기된 코드에 대한 지원은 Markdown 편집기마다 다를 수 있습니다. 확실하게 알아보려면 게시자의 특정 설명서를 확인하세요.