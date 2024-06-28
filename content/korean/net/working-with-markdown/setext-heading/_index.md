---
title: 세텍스 제목
linktitle: 세텍스 제목
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 Setext 제목을 사용하여 문서 형식을 지정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/setext-heading/
---

이 튜토리얼에서는 .NET용 Aspose.Words와 함께 Setext Heading 기능을 사용하는 방법을 안내합니다. Setext 제목은 Markdown 문서의 제목 형식을 지정하는 대체 방법입니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: Setext 제목 스타일 사용

기본 "제목 1" 단락 스타일을 사용하여 문서에 수준 1 제목을 만들겠습니다.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## 3단계: 스타일 재설정

단락 사이에 원치 않는 스타일 조합이 발생하지 않도록 이전에 적용한 글꼴 스타일을 재설정합니다.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 4단계: Setext 제목 수준 사용자 정의

기존 제목 스타일을 기반으로 새로운 단락 스타일을 추가하여 Setext 제목 수준을 사용자 정의할 수 있습니다. 이 예에서는 Setext 형식의 수준 1 제목을 나타내기 위해 "제목 1" 스타일을 기반으로 "SetextHeading1" 스타일을 만듭니다.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## 5단계: 문서 저장

마지막으로 원하는 형식으로 문서를 저장할 수 있습니다.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### .NET용 Aspose.Words를 사용하는 Setext 제목의 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// 단락 간에 스타일을 결합하지 않도록 이전 단락의 스타일을 재설정합니다.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// 단락 간에 스타일을 결합하지 않도록 이전 단락의 스타일을 재설정합니다.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// 기본 단락의 제목 수준이 2보다 큰 경우 Setex 제목 수준은 2로 재설정됩니다.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### FAQ

#### Q: Setext Markdown 헤더란 무엇입니까?

A: Setext Markdown 헤더는 Markdown 문서에서 제목을 만드는 대체 방법입니다. 다양한 수준의 제목을 표시하기 위해 밑줄 문자(= 또는 -)를 사용합니다.

#### Q: Setext Markdown 헤더를 사용하는 방법은 무엇입니까?

A: Setext Markdown 제목을 사용하려면 제목 텍스트 아래에 밑줄을 넣으세요. 수준 1 헤더에는 등호(=)를 사용하고 수준 2 헤더에는 하이픈(-)을 사용합니다.

#### Q: Setext Markdown 헤더를 사용할 때 제한 사항이 있나요?

A: Setext Markdown 제목은 제목 계층 구조 측면에서 제한이 있으며 표준 Markdown 제목만큼 시각적으로 구별되지 않습니다.

#### Q: Setext Markdown 헤더의 모양을 사용자 정의할 수 있습니까?

A: 표준 Markdown에서는 Setext Markdown 헤더의 모양을 사용자 정의할 수 없습니다. 사용된 밑줄 문자를 기반으로 미리 정의된 모양이 있습니다.

#### Q: Setext Markdown 헤더는 모든 Markdown 편집기에서 지원됩니까?

A: Setext Markdown 헤더에 대한 지원은 Markdown 편집기마다 다를 수 있습니다. 확실하게 알아보려면 게시자의 특정 설명서를 확인하세요.