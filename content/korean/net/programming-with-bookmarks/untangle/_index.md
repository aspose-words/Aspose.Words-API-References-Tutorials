---
title: Word 문서에서 풀기
linktitle: Word 문서에서 풀기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 인접한 테이블 행에 있는 단어 문서 중첩 북마크를 푸는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/untangle/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 Aspose.Words for .NET 라이브러리에서 Untangle 함수를 사용하는 방법을 이해합니다. 이 기능은 인접한 테이블 행에 중첩된 북마크를 해제합니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 문서 북마크 찾아보기

foreach 루프를 사용하여 문서에 있는 모든 북마크를 반복합니다.

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // 북마크 처리 코드는 여기에 있습니다.
}
```

## 2단계: 북마크에서 상위 행 가져오기

 우리는`GetAncestor` 북마크의 시작 및 끝 노드의 상위 행을 검색하는 방법:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## 3단계: 중첩된 북마크 풀기

두 상위 줄이 모두 발견되고 책갈피가 인접한 줄에서 시작하고 끝나는 경우 책갈피의 끝 노드를 맨 위 행에 있는 마지막 셀의 마지막 단락 끝으로 이동합니다.

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### .NET용 Aspose.Words를 사용하는 Untangle의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 중첩된 북마크를 풀기 위한 전체 소스 코드 예입니다.

```csharp

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

```

## 결론

이 기사에서는 Aspose.Words for .NET의 Untangle 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 우리는 인접한 테이블 행에 중첩된 북마크를 풀기 위한 단계별 가이드를 따랐습니다.

### FAQ

#### Q: Untangle 기능은 인접한 테이블 행에 중첩된 책갈피에서만 작동합니까?

A: 예, Untangle 기능은 인접한 테이블 행에 있는 중첩된 책갈피를 풀기 위해 특별히 설계되었습니다. 북마크가 인접 라인에 있지 않으면 이 기능은 적용되지 않습니다.

#### Q: 내 Word 문서에서 중첩된 책갈피를 어떻게 식별할 수 있나요?

A: 문서의 책갈피를 반복하고 시작 책갈피와 끝 책갈피가 인접한 테이블 행에 있는지 확인하여 중첩된 책갈피를 식별할 수 있습니다. 이 문서에 제공된 소스 코드를 시작점으로 사용하여 이 기능을 구현할 수 있습니다.

#### Q: Unscramble 기능은 원본 문서의 내용을 수정합니까?

A: 예, Untangle 기능은 책갈피의 끝 노드를 맨 위 행에 있는 마지막 셀의 마지막 단락 끝으로 이동하여 원본 문서를 수정합니다. 이 기능을 적용하기 전에 문서의 백업 복사본을 저장하세요.

#### Q: 섹션이나 단락 등 다른 유형의 문서 요소에 중첩된 책갈피를 어떻게 풀 수 있나요?

A: 이 기사에 제시된 Untangle 기능은 인접한 테이블 행에 중첩된 책갈피를 풀기 위해 특별히 설계되었습니다. 다른 문서 요소에 중첩된 책갈피를 풀려면 그에 따라 코드를 조정하고 적절한 방법을 사용하여 원하는 요소에 액세스해야 합니다.

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에서 중첩된 책갈피를 풀 수 있는 다른 방법이 있습니까?

 A: 이 문서에 제시된 방법은 인접한 테이블 행에 중첩된 책갈피를 풀기 위한 일반적인 방법입니다. 그러나 프로젝트의 특정 요구 사항에 따라 다른 접근 방식이나 기술이 있을 수 있습니다. 당신은 확인할 수 있습니다[.NET API 참조용 Aspose.Words](https://reference.aspose.com/words/net/) 사용 가능한 기능을 더 자세히 살펴보세요.