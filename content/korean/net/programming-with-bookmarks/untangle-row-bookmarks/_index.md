---
title: Word 문서에서 행 책갈피 풀기
linktitle: Word 문서에서 행 책갈피 풀기
second_title: Aspose.Words 문서 처리 API
description: Word 문서에서 중첩된 행 책갈피를 풀어 다른 책갈피에 영향을 주지 않고 특정 행을 제거하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/untangle-row-bookmarks/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 .NET용 Aspose.Words 라이브러리에서 Untangle Row Bookmarks 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 행의 북마크 끝을 북마크 시작 부분과 같은 줄에 배치할 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 문서 로드

 우리는`Document` 파일에서 기존 문서를 로드하는 클래스:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## 2단계: 라인 북마크 풀기

 우리는`Untangle` 행에서 북마크를 풀어주는 기능입니다. 이 함수는 북마크 시작과 동일한 라인에 북마크 끝을 배치하는 사용자 정의 작업을 수행합니다.

```csharp
Untangle(doc);
```

## 3단계: 북마크로 줄 삭제

 우리는`DeleteRowByBookmark` 북마크로 특정 행을 삭제하는 함수:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## 4단계: 다른 북마크의 무결성 확인

북마크의 끝이 여전히 존재하는지 확인하여 다른 북마크가 손상되지 않았는지 확인합니다.

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### .NET용 Aspose.Words를 사용하는 Untangle Row Bookmarks의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 줄에서 북마크를 풀기 위한 전체 샘플 소스 코드입니다.


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//이는 행 책갈피 끝을 책갈피 시작과 동일한 행에 배치하는 사용자 정의 작업을 수행합니다.
	Untangle(doc);

	// 이제 다른 행의 북마크를 손상시키지 않고 북마크로 쉽게 행을 삭제할 수 있습니다.
	DeleteRowByBookmark(doc, "ROW2");

	// 이는 다른 북마크가 손상되지 않았는지 확인하기 위한 것입니다.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### 소스 코드 풀기
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                // 북마크와 북마크 끝 노드의 상위 행을 가져옵니다.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // 두 행이 모두 정상적으로 발견되고 북마크 시작과 끝이 인접한 행에 포함되어 있으면
                // 책갈피 끝 노드를 맨 위 행의 마지막 셀에 있는 마지막 단락의 끝으로 이동합니다.
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### DeleteRowByBookmark 소스 코드
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## 결론

이 기사에서는 .NET용 Aspose.Words의 Untangle Row Bookmarks 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 우리는 행 북마크를 풀고 다른 북마크를 손상시키지 않고 특정 행을 삭제하는 단계별 가이드를 따랐습니다.

### Word 문서의 행 북마크 풀기에 대한 FAQ

#### Q: Unscramble Row Bookmarks는 테이블의 행 북마크에서만 작동합니까?

A: 예, Untangle Row Bookmarks 기능은 테이블에 있는 행 책갈피를 풀기 위해 특별히 설계되었습니다. 이 함수는 배열의 줄 책갈피를 처리하고 책갈피 끝이 책갈피 시작과 동일한 줄에 있는지 확인하는 데 사용할 수 있습니다.

#### Q: Unscramble Line Bookmarks 기능은 원본 문서의 내용을 수정합니까?

A: 네, 스크램블 라인 북마크 기능은 라인 북마크의 끝을 이동하여 북마크의 시작 부분과 동일한 라인에 배치함으로써 원본 문서를 수정합니다. 이 기능을 적용하기 전에 문서의 백업 복사본을 저장하세요.

#### Q: Word 문서에서 줄 책갈피를 어떻게 식별할 수 있나요?

A: 행 책갈피는 일반적으로 테이블에서 특정 섹션을 표시하는 데 사용됩니다. 문서의 책갈피를 탐색하고 책갈피가 테이블 행에 있는지 확인하여 행 책갈피를 식별할 수 있습니다.

#### Q: 인접하지 않은 테이블의 행 북마크를 풀 수 있나요?

A: 이 문서에 제시된 Untangle Row Bookmarks 기능은 인접한 테이블의 행 책갈피를 풀기 위해 설계되었습니다. 인접하지 않은 테이블의 행 책갈피를 풀려면 문서 구조에 따라 코드에 대한 추가 조정이 필요할 수 있습니다.

#### Q: 행 북마크가 풀린 후 행 북마크에 대해 어떤 다른 조작을 수행할 수 있습니까?

A: 라인 북마크가 풀리면 필요에 따라 다양한 조작을 수행할 수 있습니다. 여기에는 북마크된 줄의 내용 편집, 삭제 또는 추가가 포함될 수 있습니다. 문서의 나머지 부분에 원치 않는 영향을 주지 않도록 라인 북마크를 주의해서 처리하십시오.