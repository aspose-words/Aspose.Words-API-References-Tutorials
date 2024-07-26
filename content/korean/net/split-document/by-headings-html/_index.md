---
title: 제목 HTML로 Word 문서 분할
linktitle: 제목 HTML로
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words의 HTML 기능을 제목으로 하여 분할 단어 문서의 C# 소스 코드를 설명하는 단계별 가이드
type: docs
weight: 10
url: /ko/net/split-document/by-headings-html/
---
이 튜토리얼에서는 Aspose.Words for .NET의 HTML 제목별 기능을 사용하여 Word 문서를 더 작은 부분으로 분할하는 방법을 안내합니다. 아래 단계에 따라 소스 코드를 이해하고 제목을 기반으로 별도의 HTML 문서를 생성하세요.

## 1단계: 문서 로드

시작하려면 문서의 디렉터리를 지정하고 문서를 Document 객체에 로드하세요. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## 2단계: HTML 형식의 제목별로 문서 나누기

이제 HTML 형식의 제목을 기반으로 문서를 더 작은 부분으로 분할하는 저장 옵션을 설정하겠습니다. 방법은 다음과 같습니다.

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// 문서를 더 작은 부분으로 분할합니다. 이 경우 제목별로 구분합니다.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### .NET용 Aspose.Words를 사용하는 By Headings HTML의 예제 소스 코드

다음은 .NET용 Aspose.Words의 By HTML Heading 기능에 대한 전체 소스 코드입니다:

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// 문서를 더 작은 부분으로 분할합니다(이 경우 제목별로 분할).
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

이 코드를 사용하면 제목을 기준으로 .NET용 Aspose.Words를 사용하여 Word 문서를 더 작은 부분으로 분할할 수 있습니다. 그런 다음 각 부분에 대해 별도의 HTML 문서를 생성할 수 있습니다.

## 결론

 이 튜토리얼에서는 Aspose.Words for .NET의 By HTML Heading 기능을 사용하여 Word 문서를 더 작은 부분으로 분할하는 방법을 배웠습니다. 지정함으로써`DocumentSplitCriteria` ~처럼`HeadingParagraph` 에서`HtmlSaveOptions`, 원본 문서에 있는 제목을 기반으로 별도의 HTML 문서를 생성할 수 있었습니다.

제목별로 문서를 분할하면 콘텐츠를 구성하고 관리하는 데 유용할 수 있으며, 특히 여러 섹션이 있는 대규모 문서의 경우 더욱 그렇습니다. Aspose.Words for .NET은 문서 분할을 처리하고 다양한 형식의 출력을 생성하기 위한 안정적이고 효율적인 솔루션을 제공합니다.

Aspose.Words for .NET에서 제공하는 추가 기능과 옵션을 자유롭게 탐색하여 문서 처리 기능을 더욱 향상시키고 작업 흐름을 간소화하세요.

### 자주 묻는 질문

#### .NET용 Aspose.Words를 사용하여 제목을 기반으로 Word 문서를 더 작은 부분으로 분할하려면 어떻게 해야 합니까?

 제목을 기준으로 Word 문서를 분할하려면 Aspose.Words for .NET의 HTML 제목별 기능을 사용할 수 있습니다. 제공된 소스 코드를 따르고`DocumentSplitCriteria` 에게`HeadingParagraph` 에서`HtmlSaveOptions` 물체. 이렇게 하면 문서가 각 제목에서 더 작은 부분으로 분할됩니다.

#### Word 문서를 어떤 형식으로 분할할 수 있나요?

 제공된 소스 코드는 Word 문서를 HTML 형식의 더 작은 부분으로 분할하는 방법을 보여줍니다. 그러나 .NET용 Aspose.Words는 DOCX, PDF, EPUB 등을 포함한 다양한 출력 형식을 지원합니다. 코드를 수정하고 원하는 출력 형식을 지정할 수 있습니다.`HtmlSaveOptions` 이에 따라 이의를 제기합니다.

#### 문서 분할 기준을 다르게 선택할 수 있나요?

예, 요구 사항에 따라 문서 분할에 대한 다른 기준을 선택할 수 있습니다. .NET용 Aspose.Words는 다음과 같은 몇 가지 기준 옵션을 제공합니다.`HeadingParagraph`, `Page`, `Section` , 그리고 더. 수정하다`DocumentSplitCriteria` 에 있는 재산`HtmlSaveOptions` 개체를 사용하여 적절한 분할 기준을 선택합니다.

#### 분할된 부분에 대한 출력 HTML을 어떻게 사용자 정의할 수 있나요?

 Aspose.Words for .NET을 사용하면 다음에서 추가 옵션을 지정하여 분할 부분에 대한 출력 HTML을 사용자 정의할 수 있습니다.`HtmlSaveOptions` 물체. CSS 스타일, 이미지, 글꼴 등과 같은 다양한 측면을 제어할 수 있습니다. HTML 출력 사용자 정의에 대한 자세한 내용은 Aspose.Words 문서를 참조하세요.

#### 여러 기준에 따라 문서를 분할할 수 있나요?

 예, 기준 옵션을 적절하게 결합하여 여러 기준에 따라 문서를 분할할 수 있습니다. 예를 들어, 제목과 페이지로 문서를 분할할 수 있습니다.`DocumentSplitCriteria`재산`HeadingParagraph | Page`. 이렇게 하면 문서가 각 제목과 페이지로 분할되어 두 기준에 따라 더 작은 부분이 생성됩니다.