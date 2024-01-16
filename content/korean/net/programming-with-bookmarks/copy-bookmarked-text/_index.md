---
title: Word 문서에서 북마크된 텍스트 복사
linktitle: Word 문서에서 북마크된 텍스트 복사
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서의 북마크 텍스트를 다른 문서에 복사하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/copy-bookmarked-text/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 .NET용 Aspose.Words 라이브러리에서 북마크된 텍스트 복사 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 원본 문서의 특정 책갈피 내용을 다른 문서로 복사할 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 원본 문서 로드

 북마크 텍스트를 복사하기 전에 소스 문서를`Document` 파일 경로를 사용하는 객체:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## 2단계: 소스 북마크 가져오기

 우리는`Bookmarks` 복사하려는 특정 책갈피를 가져오려면 소스 문서 범위의 속성을 사용하세요.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## 3단계: 대상 문서 만들기

북마크 내용을 복사하기 위한 대상 문서 역할을 할 새 문서를 만듭니다.

```csharp
Document dstDoc = new Document();
```

## 4단계: 복사 위치 지정

복사한 텍스트를 추가할 위치를 지정합니다. 이 예에서는 대상 문서의 마지막 섹션 본문 끝에 텍스트를 추가합니다.

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## 5단계: 북마크 텍스트 가져오기 및 복사

 우리는`NodeImporter`북마크 텍스트를 원본 문서에서 대상 문서로 가져오고 복사하는 개체:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### .NET용 Aspose.Words를 사용하여 북마크된 텍스트 복사에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 북마크에서 텍스트를 복사하는 방법을 보여주는 전체 예제 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// 내용을 복사하려는 북마크입니다.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// 이 문서에 추가할 예정입니다.
	Document dstDoc = new Document();

	// 마지막 섹션의 본문 끝에 추가한다고 가정해 보겠습니다.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// 단일 컨텍스트 없이 여러 번 가져오면 많은 스타일이 생성됩니다.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AppendBookmarkedText 소스 코드

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // 북마크의 시작 부분을 포함하는 단락입니다.
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // 북마크의 끝 부분을 포함하는 단락입니다.
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // 합리적으로 간단한 시나리오로 제한하십시오.
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // 시작 단락부터 끝 단락까지(및 포함) 모든 단락을 복사하고 싶습니다.
            // 따라서 우리가 멈추는 노드는 끝 단락 다음의 노드입니다.
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //그러면 현재 노드의 복사본이 생성되고 컨텍스트에서 이를 가져옵니다(유효하게 만듭니다).
                // 대상 문서의 가져오기란 스타일과 목록 식별자를 올바르게 조정하는 것을 의미합니다.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## 결론

이 기사에서는 .NET용 Aspose.Words에서 북마크된 텍스트 복사 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 우리는 단계별 가이드에 따라 소스 문서의 북마크 내용을 다른 문서로 복사했습니다.

### Word 문서에서 북마크된 텍스트 복사에 대한 FAQ

#### Q: Aspose.Words for .NET에서 "북마크와 함께 텍스트 복사" 기능을 사용하기 위한 요구 사항은 무엇입니까?

A: Aspose.Words for .NET의 "책갈피와 함께 텍스트 복사" 기능을 사용하려면 C# 언어에 대한 기본 지식이 필요합니다. 또한 Aspose.Words 라이브러리가 설치된 .NET 개발 환경이 필요합니다.

#### Q: .NET용 Aspose.Words에 소스 문서를 어떻게 로드합니까?

 A: .NET용 Aspose.Words에서 소스 문서를 로드하려면 다음을 사용할 수 있습니다.`Document` 문서의 파일 경로를 지정하여 클래스를 지정합니다. 다음은 샘플 코드입니다.

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Q: Aspose.Words for .NET을 사용하여 소스 문서에서 특정 북마크의 내용을 가져오는 방법은 무엇입니까?

 A: Aspose.Words for .NET을 사용하여 소스 문서의 특정 북마크 내용을 얻으려면`Bookmarks` 소스 문서 범위의 속성을 사용하고 북마크 이름을 사용하여 특정 북마크를 검색합니다. 다음은 샘플 코드입니다.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Q: Aspose.Words for .NET을 사용하여 대상 문서에서 북마크 텍스트 복사본의 위치를 지정하는 방법은 무엇입니까?

 A: Aspose.Words for .NET을 사용하여 대상 문서에서 복사된 책갈피 텍스트를 추가할 위치를 지정하려면 대상 문서의 마지막 섹션 본문으로 이동할 수 있습니다. 당신은 사용할 수 있습니다`LastSection` 마지막 섹션에 액세스하는 속성과`Body` 해당 섹션의 본문에 액세스하는 속성입니다. 다음은 샘플 코드입니다.

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Q: Aspose.Words for .NET을 사용하여 원본 문서에서 대상 문서로 책갈피 텍스트를 가져오고 복사하는 방법은 무엇입니까?

 A: Aspose.Words for .NET을 사용하여 원본 문서에서 대상 문서로 책갈피 텍스트를 가져오고 복사하려면 다음을 사용할 수 있습니다.`NodeImporter` 원본 문서, 대상 문서 및 유지할 서식 모드를 지정하는 클래스입니다. 그런 다음`AppendBookmarkedText` 대상 문서에 북마크 텍스트를 추가하는 방법입니다. 다음은 샘플 코드입니다.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Q: Aspose.Words for .NET을 사용하여 북마크 텍스트를 복사한 후 대상 문서를 저장하는 방법은 무엇입니까?

A: Aspose.Words for .NET을 사용하여 북마크에서 텍스트를 복사한 후 대상 문서를 저장하려면 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 대상 파일 경로를 지정하는 객체입니다. 다음은 샘플 코드입니다.

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```