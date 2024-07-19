---
title: Word 문서에 북마크된 텍스트 추가
linktitle: Word 문서에 북마크된 텍스트 추가
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에 북마크된 텍스트를 추가하는 방법을 알아보세요. 개발자에게 적합합니다.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/append-bookmarked-text/
---
## 소개

안녕하세요! Word 문서의 북마크된 섹션에서 텍스트를 추가하려고 시도했지만 까다로웠던 적이 있습니까? 당신은 운이 좋다! 이 튜토리얼은 .NET용 Aspose.Words를 사용하는 과정을 안내합니다. 쉽게 따라할 수 있도록 간단한 단계로 나누어 보겠습니다. 전문가처럼 북마크된 텍스트를 추가해 보세요!

## 전제조건

시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

-  .NET용 Aspose.Words: 설치되어 있는지 확인하세요. 그렇지 않다면 할 수 있습니다[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 모든 .NET 개발 환경.
- C# 기본 지식: 기본 C# 프로그래밍 개념을 이해하는 것이 도움이 됩니다.
- 책갈피가 있는 Word 문서: 텍스트를 추가하는 데 사용할 책갈피가 설정된 Word 문서입니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이렇게 하면 필요한 모든 도구를 손쉽게 사용할 수 있습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

예제를 세부 단계로 나누어 보겠습니다.

## 1단계: 문서 로드 및 변수 초기화

좋습니다. Word 문서를 로드하고 필요한 변수를 초기화하는 것부터 시작해 보겠습니다.

```csharp
// 원본 및 대상 문서를 로드합니다.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// 문서 가져오기 도구를 초기화합니다.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// 소스 문서에서 북마크를 찾으세요.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## 2단계: 시작 및 끝 단락 식별

이제 북마크가 시작되고 끝나는 단락을 찾아보겠습니다. 이 범위 내에서 텍스트를 처리해야 하므로 이는 매우 중요합니다.

```csharp
// 북마크의 시작 부분을 포함하는 단락입니다.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// 북마크의 끝 부분을 포함하는 단락입니다.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## 3단계: 단락 상위 유효성 검사

시작 문단과 끝 문단의 상위 문단이 동일한지 확인해야 합니다. 이는 일을 간단하게 유지하기 위한 간단한 시나리오입니다.

```csharp
// 합리적으로 간단한 시나리오로 제한하십시오.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## 4단계: 중지할 노드 식별

다음으로 텍스트 복사를 중지할 노드를 결정해야 합니다. 이는 끝 단락 바로 뒤의 노드가 됩니다.

```csharp
// 시작 단락부터 끝 단락까지(및 포함) 모든 단락을 복사하고 싶습니다.
// 따라서 우리가 멈추는 노드는 끝 단락 다음의 노드입니다.
Node endNode = endPara.NextSibling;
```

## 5단계: 대상 문서에 북마크된 텍스트 추가

마지막으로 시작 단락부터 끝 단락 뒤의 노드까지 노드를 반복하여 대상 문서에 추가해 보겠습니다.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // 그러면 현재 노드의 복사본이 생성되고 컨텍스트에서 이를 가져옵니다(유효하게 만듭니다).
    // 대상 문서의 가져오기란 스타일과 목록 식별자를 올바르게 조정하는 것을 의미합니다.
    Node newNode = importer.ImportNode(curNode, true);

    // 가져온 노드를 대상 문서에 추가합니다.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// 추가된 텍스트와 함께 대상 문서를 저장합니다.
dstDoc.Save("appended_document.docx");
```

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서의 북마크된 섹션에서 텍스트를 성공적으로 추가했습니다. 이 강력한 도구를 사용하면 문서를 쉽게 조작할 수 있으며 이제 한 가지 트릭을 더 사용할 수 있습니다. 즐거운 코딩하세요!

## FAQ

### 여러 북마크의 텍스트를 한 번에 추가할 수 있나요?
예, 각 북마크에 대해 프로세스를 반복하고 그에 따라 텍스트를 추가할 수 있습니다.

### 시작 문단과 끝 문단의 상위 문단이 다른 경우에는 어떻게 되나요?
현재 예에서는 동일한 상위가 있다고 가정합니다. 다른 부모의 경우 더 복잡한 처리가 필요합니다.

### 첨부된 텍스트의 원래 서식을 유지할 수 있나요?
 전적으로! 그만큼`ImportFormatMode.KeepSourceFormatting` 원래 형식이 유지되는지 확인합니다.

### 대상 문서의 특정 위치에 텍스트를 추가할 수 있습니까?
예, 대상 문서에서 원하는 노드로 이동하여 원하는 위치에 텍스트를 추가할 수 있습니다.

### 책갈피의 텍스트를 새 섹션에 추가해야 하면 어떻게 합니까?
대상 문서에 새 섹션을 만들고 거기에 텍스트를 추가할 수 있습니다.