---
title: Word 문서에서 북마크된 텍스트 복사
linktitle: Word 문서에서 북마크된 텍스트 복사
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서 간에 북마크된 텍스트를 쉽게 복사할 수 있습니다. 이 단계별 가이드를 통해 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/copy-bookmarked-text/
---
## 소개

한 Word 문서에서 다른 Word 문서로 특정 섹션을 복사해야 했던 적이 있습니까? 글쎄, 당신은 운이 좋다! 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 북마크된 텍스트를 한 Word 문서에서 다른 Word 문서로 복사하는 방법을 안내합니다. 동적 보고서를 작성하든 문서 생성을 자동화하든 이 가이드는 프로세스를 단순화합니다.

## 전제조건

자세히 알아보기 전에 다음 사항이 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words: 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio 또는 기타 .NET 개발 환경.
- C#에 대한 기본 지식: C# 프로그래밍 및 .NET 프레임워크에 대한 지식.

## 네임스페이스 가져오기

시작하려면 프로젝트에 필요한 네임스페이스를 가져왔는지 확인하세요.

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## 1단계: 원본 문서 로드

먼저 복사하려는 북마크 텍스트가 포함된 소스 문서를 로드해야 합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 여기,`dataDir` 문서 디렉토리의 경로입니다.`Bookmarks.docx` 원본 문서입니다.

## 2단계: 북마크 식별

다음으로, 원본 문서에서 복사하려는 북마크를 식별하세요.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 바꾸다`"MyBookmark1"` 북마크의 실제 이름으로.

## 3단계: 대상 문서 만들기

이제 북마크된 텍스트를 복사할 새 문서를 만듭니다.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## 4단계: 북마크된 콘텐츠 가져오기

 스타일과 서식을 유지하려면 다음을 사용하세요.`NodeImporter` 북마크된 콘텐츠를 소스 문서에서 대상 문서로 가져옵니다.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## 5단계: AppendBookmarkedText 메서드 정의

여기서 마법이 일어납니다. 북마크된 텍스트 복사를 처리하는 방법을 정의합니다.

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## 6단계: 대상 문서 저장

마지막으로 대상 문서를 저장하여 복사된 내용을 확인합니다.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## 결론

그리고 그게 다야! .NET용 Aspose.Words를 사용하여 한 Word 문서에서 다른 Word 문서로 북마크된 텍스트를 성공적으로 복사했습니다. 이 방법은 문서 조작 작업을 자동화하여 작업 흐름을 더욱 효율적이고 간소화하는 데 강력합니다.

## FAQ

### 여러 북마크를 한 번에 복사할 수 있나요?
예, 여러 북마크를 반복하고 동일한 방법을 사용하여 각 북마크를 복사할 수 있습니다.

### 북마크를 찾을 수 없으면 어떻게 되나요?
 그만큼`Range.Bookmarks` 재산이 돌아올 것이다`null`이므로 예외가 발생하지 않도록 이 사례를 처리해야 합니다.

### 원래 북마크의 형식을 유지할 수 있나요?
 전적으로! 사용`ImportFormatMode.KeepSourceFormatting` 원래 형식이 유지되는지 확인합니다.

### 북마크된 텍스트의 크기에 제한이 있나요?
특별한 제한은 없지만 매우 큰 문서의 경우 성능이 달라질 수 있습니다.

### 서로 다른 Word 문서 형식 간에 텍스트를 복사할 수 있나요?
예, Aspose.Words는 다양한 Word 형식을 지원하며 이 방법은 이러한 형식에서 작동합니다.