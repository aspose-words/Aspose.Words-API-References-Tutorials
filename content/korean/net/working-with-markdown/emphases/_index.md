---
title: 강조점
linktitle: 강조점
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드에서 강조(굵게 및 기울임꼴)를 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/emphases/
---

이 예에서는 Aspose.Words for .NET에서 강조를 사용하는 방법을 설명합니다. 강조는 볼드체, 이탤릭체 등 텍스트의 특정 부분을 강조하는 데 사용됩니다.

## 1단계: 문서 초기화

 먼저, 인스턴스를 생성하여 문서를 초기화하겠습니다.`Document` 수업.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 2단계: 문서 생성기 사용

다음으로 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 강조를 사용하여 텍스트 추가

문서 생성기의 글꼴 속성을 변경하여 강조 텍스트를 추가할 수 있습니다. 이 예에서는 텍스트의 다양한 부분을 강조하기 위해 볼드체와 이탤릭체를 사용했습니다.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## 4단계: 문서 저장

 마지막으로 원하는 형식으로 문서를 저장할 수 있습니다. 이 예에서는`.md` Markdown 형식의 확장입니다.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

축하합니다! 이제 Aspose.Words for .NET에서 강조를 사용하는 방법을 배웠습니다.

### .NET용 Aspose.Words를 사용하는 Emphases의 예제 소스 코드


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### FAQ

#### Q: Markdown을 사용하여 텍스트를 강조하려면 어떻게 해야 합니까?

A: Markdown을 사용하여 텍스트를 강조 표시하려면 적절한 기호로 텍스트를 둘러싸면 됩니다. 사용`*` 또는`_` 이탤릭체의 경우,`**` 또는`__` 굵게 표시하고`~~` 취소선을 위해.

#### Q: 동일한 텍스트에 서로 다른 하이라이트를 결합할 수 있나요?

 A: 예, 동일한 텍스트에 서로 다른 하이라이트를 결합하는 것이 가능합니다. 예를 들어, 두 단어를 모두 사용하여 단어를 굵게 표시하고 기울임꼴로 표시할 수 있습니다.`**` 그리고`*` 단어 주위에.

#### Q: Markdown에서는 어떤 강조 옵션을 사용할 수 있나요?

A: Markdown에서 사용할 수 있는 강조 옵션은 기울임체(`*` 또는`_`), 용감한 (`**` 또는`__`) 및 취소선(`~~`).

#### Q: 강조 표시를 위해 Markdown에서 사용하는 특수 문자가 텍스트에 포함된 경우를 어떻게 처리합니까?

 A: 텍스트에 Markdown에서 강조 표시를 위해 사용하는 특수 문자가 포함되어 있는 경우 앞에 기호를 붙여서 이스케이프할 수 있습니다.`\` . 예를 들어,`\*` 문자 그대로 별표가 표시됩니다.

#### Q: CSS를 사용하여 강조표시 모양을 맞춤설정할 수 있나요?

A: Markdown의 강조 표시는 일반적으로 브라우저의 기본 스타일을 사용하여 렌더링됩니다. 마크다운을 HTML로 변환하면 CSS 규칙을 사용하여 강조 표시 모양을 사용자 정의할 수 있습니다.