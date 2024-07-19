---
title: 인라인 코드
linktitle: 인라인 코드
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 코드를 인라인하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/inline-code/
---

이 예에서는 Aspose.Words for .NET에서 인라인 코드 기능을 사용하는 방법을 안내합니다. 인라인 코드는 단락 내의 코드 조각을 시각적으로 표현하는 데 사용됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 인라인 코드에 대한 스타일 추가

 다음을 사용하여 인라인 코드에 대한 사용자 정의 스타일을 추가하겠습니다.`Styles.Add` 의 방법`Document` 물체. 이 예에서는 기본 백틱이 있는 인라인 코드에 대해 "InlineCode"라는 스타일을 만듭니다.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## 3단계: 인라인 코드 추가

이제 "InlineCode" 사용자 정의 스타일을 사용하여 인라인 코드를 추가할 수 있습니다. 이 예에서는 백틱 수가 다른 두 개의 텍스트를 추가합니다.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### .NET용 Aspose.Words를 사용한 인라인 코드의 예제 소스 코드

```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 백틱 수가 누락되었습니다. 기본적으로 백틱 1개가 사용됩니다.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// 3개의 백틱이 있을 것입니다.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

축하합니다! 이제 Aspose.Words for .NET에서 인라인 코드 기능을 사용하는 방법을 배웠습니다.


### FAQ

#### Q: Aspose.Words에서 인라인 코드를 어떻게 사용할 수 있나요?

A: Aspose.Words에서 인라인 코드를 사용하려면 적절한 태그를 사용하여 인라인 코드 형식으로 지정할 텍스트를 둘러싸면 됩니다. 예를 들어 다음을 사용할 수 있습니다.`<code>` 또는`<kbd>` 인라인 코드로 서식을 지정할 텍스트를 둘러싸는 태그입니다.

#### Q: Aspose.Words에서 인라인 코드 글꼴이나 색상을 지정할 수 있나요?

 A: 예, Aspose.Words에서 인라인 코드의 글꼴이나 색상을 지정할 수 있습니다. 당신은 사용할 수 있습니다`Font.Name`그리고`Font.Color` 의 속성`Run` 인라인 코드의 글꼴과 색상을 설정하는 개체입니다. 예를 들어 다음을 사용할 수 있습니다.`run.Font.Name = "Courier New"` 인라인 코드의 글꼴을 지정하고`run.Font.Color = Color.Blue` 색상을 지정합니다.

#### Q: 다른 텍스트 요소가 포함된 단락에 인라인 코드를 사용할 수 있습니까?

 A: 예, 다른 텍스트 요소가 포함된 단락에서 인라인 코드를 사용할 수 있습니다. 여러 개 만들 수 있습니다.`Run` 단락의 여러 부분을 나타내는 개체를 사용한 다음 인라인 코드 태그를 사용하여 특정 부분만 인라인 코드로 서식을 지정합니다. 그런 다음 다음을 사용하여 단락에 추가할 수 있습니다.`Paragraph.AppendChild(run)` 방법.