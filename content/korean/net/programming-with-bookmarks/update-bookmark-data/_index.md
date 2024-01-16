---
title: Word 문서에서 책갈피 데이터 업데이트
linktitle: 북마크 데이터 업데이트
second_title: Aspose.Words 문서 처리 API
description: .NET용 Word 문서 기능에서 Aspose.Words 북마크 데이터 업데이트의 C# 소스 코드를 설명하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/update-bookmark-data/
---

이 튜토리얼에서는 .NET용 Aspose.Words의 워드 문서 기능에서 북마크 데이터 업데이트를 이해하고 구현하기 위한 단계별 가이드를 안내합니다. 이 기능을 사용하면 C# 소스 코드를 사용하여 Word 문서 내의 책갈피 내용과 속성을 업데이트할 수 있습니다.

## 요구사항

튜토리얼을 진행하기 전에 다음 요구 사항이 충족되었는지 확인하세요.

- .NET 라이브러리용 Aspose.Words 설치됨
- C# 프로그래밍 언어에 대한 기본 지식
- Visual Studio 또는 기타 호환 IDE

## 1단계: 문서 넣기

이 단계에서는 업데이트하려는 북마크가 포함된 Word 문서를 로드합니다. 문서가 특정 디렉터리에 저장되어 있다고 가정하고 다음 코드를 사용하여 문서를 로드합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 실제 디렉토리 경로를 사용합니다.

## 2단계: 북마크에 액세스

북마크 데이터를 업데이트하려면 먼저 문서 내의 특정 북마크에 액세스해야 합니다. 각 북마크에는 고유한 이름이 연결되어 있습니다. 다음 코드를 사용하여 "MyBookmark1"이라는 책갈피에 액세스합니다.

```csharp
Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];
```

북마크 이름이 문서의 이름과 일치하는지 확인하세요. 귀하의 요구 사항에 따라 수정할 수 있습니다.

## 3단계: 북마크 속성 및 콘텐츠 업데이트

북마크에 액세스하면 해당 속성과 콘텐츠를 업데이트할 수 있습니다. 다음 코드 조각에서는 북마크 이름과 텍스트를 업데이트합니다.

```csharp
string name = bookmark.Name;
string text = bookmark.Text;

bookmark.Name = "RenamedBookmark";
bookmark.Text = "This is a new bookmarked text.";
```

필요에 따라 책갈피 이름과 새 텍스트를 사용자 정의할 수 있습니다. 위의 코드는 북마크의 이름을 "RenamedBookmark"로 바꾸고 텍스트 내용을 업데이트합니다.

## 4단계: 업데이트된 문서 저장

북마크 데이터를 업데이트한 후 수정된 문서를 저장해야 합니다. 문서를 저장하려면 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "UpdatedDocument.docx");
```

이 코드는 수정된 문서를 원본 문서와 동일한 디렉터리에 "UpdatedDocument.docx"라는 이름으로 저장합니다.

### .NET용 Aspose.Words를 사용하여 북마크 데이터 업데이트에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];

	string name = bookmark.Name;
	string text = bookmark.Text;

	bookmark.Name = "RenamedBookmark";
	bookmark.Text = "This is a new bookmarked text.";

```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 실제 디렉토리 경로를 사용합니다.

## 결론

축하해요! Aspose.Words for .NET을 사용하여 북마크 데이터를 업데이트하는 방법을 성공적으로 배웠습니다. 이 자습서에서 제공되는 단계별 가이드를 따르면 이제 이 기능을 C# 응용 프로그램에 통합하고 Word 문서 내의 책갈피를 프로그래밍 방식으로 조작할 수 있습니다.

### Word 문서의 북마크 데이터 업데이트에 대한 FAQ

#### Q: 북마크 데이터 업데이트 기능은 Word 문서의 북마크에서만 작동합니까?

A: 예, 책갈피 데이터 업데이트 기능은 Word 문서의 책갈피용으로 특별히 설계되었습니다. Word 문서에서 책갈피의 내용과 속성을 업데이트할 수 있습니다.

#### Q: 텍스트 외에 다른 북마크 속성을 업데이트할 수 있나요?

 A: 예, 텍스트 외에도 북마크 이름, 북마크 범위 등과 같은 다른 북마크 속성을 업데이트할 수도 있습니다.`Bookmark` 원하는 속성을 업데이트하는 개체입니다.

#### Q: 동일한 문서에서 여러 북마크를 업데이트할 수 있나요?

A: 예, 각 북마크에 대해 액세스 및 업데이트 단계를 반복하여 동일한 문서에서 여러 북마크를 업데이트할 수 있습니다. 업데이트하려는 각 책갈피에 대해 고유한 책갈피 이름을 사용해야 합니다.

#### Q: 북마크 데이터 업데이트 기능이 원본 문서를 수정하나요?

A: 예, 북마크 데이터 업데이트 기능은 북마크 속성과 콘텐츠를 업데이트하여 원본 문서를 수정합니다. 이 기능을 적용하기 전에 원본 문서의 복사본을 저장하세요.