---
title: Word 문서에서 책갈피로 행 삭제
linktitle: Word 문서에서 책갈피로 행 삭제
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서의 특정 책갈피를 기반으로 테이블 행을 삭제하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/delete-row-by-bookmark/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 .NET 라이브러리용 Aspose.Words에서 책갈피별 행 삭제 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 Word 문서의 특정 책갈피를 기반으로 표 행을 삭제할 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 북마크 가져오기

 우리는`Bookmarks` 문서 범위의 속성을 사용하여 테이블 행을 삭제하는 데 사용할 특정 책갈피를 가져옵니다.

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## 2단계: 테이블 행 삭제

 우리는`GetAncestor` 을 얻는 방법`Row` 북마크의 상위 요소를 입력하세요. 다음으로 우리는`Remove` 테이블 행을 제거하는 방법:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### .NET용 Aspose.Words를 사용하여 책갈피로 행 삭제에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 특정 책갈피를 기반으로 테이블 행을 삭제하는 방법을 보여주는 전체 샘플 소스 코드입니다.

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## 결론

이 기사에서는 .NET용 Aspose.Words의 책갈피별 행 삭제 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 문서의 특정 책갈피를 기반으로 테이블 행을 삭제하는 단계별 지침을 따랐습니다.

### Word 문서에서 북마크로 행 삭제에 대한 FAQ

#### Q: 동일한 북마크를 사용하여 여러 행을 삭제할 수 있나요?

A: 예, 동일한 북마크를 사용하여 여러 행을 삭제할 수 있습니다. 그러나 삭제할 행 수를 결정하고 제공된 코드 조각에 필요한 조정을 수행하려면 코드에서 논리를 처리해야 합니다.

#### Q: 문서에 북마크가 없으면 어떻게 되나요?

A: 지정된 책갈피가 문서에 없으면 코드 조각은 책갈피 개체에 대해 null 값을 반환합니다. 따라서 테이블 행을 삭제하기 전에 적절한 검사를 추가하여 코드에서 이 시나리오를 처리해야 합니다.

#### Q: Aspose.Words 라이브러리는 무료로 사용할 수 있나요?

 A: Aspose.Words 라이브러리는 상업용 라이브러리이므로 프로젝트에서 사용하려면 유효한 라이센스가 필요할 수 있습니다. 당신은 방문 할 수 있습니다[.NET API 참조용 Aspose.Words](https://reference.aspose.com/words/net/) 라이선스 옵션 및 가격에 대해 자세히 알아보세요.

#### Q: Word 문서의 특정 섹션에 있는 표의 행을 삭제할 수 있나요?

A: 예, Word 문서의 특정 섹션에 있는 표의 행을 삭제할 수 있습니다. 해당 섹션 내의 적절한 범위나 책갈피를 사용하여 특정 섹션을 대상으로 하도록 제공된 코드 조각을 수정할 수 있습니다.