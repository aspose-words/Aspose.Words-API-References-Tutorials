---
title: Word 문서에 북마크 만들기
linktitle: Word 문서에 북마크 만들기
second_title: Aspose.Words 문서 처리 API
description: 이 상세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 북마크를 만드는 방법을 알아보세요. 문서 탐색 및 정리에 적합합니다.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/create-bookmark/
---
## 소개

Word 문서에 책갈피를 만드는 것은 특히 큰 문서를 쉽게 탐색하려는 경우 게임 체인저가 될 수 있습니다. 오늘은 Aspose.Words for .NET을 사용하여 북마크를 만드는 과정을 살펴보겠습니다. 이 튜토리얼에서는 프로세스의 각 부분을 이해할 수 있도록 단계별로 안내합니다. 그럼 바로 들어가 보겠습니다!

## 전제 조건

시작하기 전에 다음이 필요합니다.

1.  .NET 라이브러리용 Aspose.Words: 다음에서 다운로드하고 설치하세요.[여기](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio 또는 기타 .NET 개발 환경.
3. C# 기본 지식: 기본 C# 프로그래밍 개념을 이해합니다.

## 네임스페이스 가져오기

.NET용 Aspose.Words를 사용하려면 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: 문서 및 DocumentBuilder 설정

문서 초기화

먼저 새 문서를 만들고 초기화해야 합니다.`DocumentBuilder`. 이는 문서에 콘텐츠와 책갈피를 추가하기 위한 시작점입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 설명:`Document` 객체는 캔버스입니다. 그만큼`DocumentBuilder` 펜과 같아서 문서에 내용을 쓰고 책갈피를 만들 수 있습니다.

## 2단계: 기본 북마크 만들기

기본 북마크 시작 및 종료

북마크를 생성하려면 시작점과 끝점을 지정해야 합니다. 여기서는 "My Bookmark"라는 북마크를 생성하겠습니다.

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");
```

 설명:`StartBookmark` 메소드는 북마크의 시작을 표시하고`Writeln` 북마크 내에 텍스트를 추가합니다.

## 3단계: 중첩된 책갈피 만들기

기본 책갈피 안에 중첩된 책갈피 추가

다른 책갈피 안에 책갈피를 중첩할 수 있습니다. 여기서는 "내 북마크" 내에 "중첩 북마크"를 추가합니다.

```csharp
builder.StartBookmark("Nested Bookmark");
builder.Writeln("Text inside a NestedBookmark.");
builder.EndBookmark("Nested Bookmark");
```

 설명: 책갈피를 중첩하면 보다 체계적이고 계층적인 콘텐츠 구성이 가능해집니다. 그만큼`EndBookmark` 메소드는 현재 북마크를 닫습니다.

## 4단계: 중첩된 책갈피 외부에 텍스트 추가

계속해서 콘텐츠를 추가하세요

중첩된 북마크 이후에 기본 북마크 내에 더 많은 콘텐츠를 계속 추가할 수 있습니다.

```csharp
builder.Writeln("Text after Nested Bookmark.");
builder.EndBookmark("My Bookmark");
```

설명: 이렇게 하면 기본 책갈피가 중첩된 책갈피와 추가 텍스트를 모두 포함하게 됩니다.

## 5단계: PDF 저장 옵션 구성

책갈피에 대한 PDF 저장 옵션 설정

문서를 PDF로 저장할 때 책갈피를 포함하도록 옵션을 구성할 수 있습니다.

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);
```

 설명:`PdfSaveOptions` 클래스를 사용하면 문서를 PDF로 저장하는 방법을 지정할 수 있습니다. 그만큼`BookmarksOutlineLevels` 속성은 PDF에서 책갈피의 계층 구조를 정의합니다.

## 6단계: 문서 저장

문서를 PDF로 저장

마지막으로 지정된 옵션으로 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

 설명:`Save` 메서드는 문서를 지정된 형식과 위치에 저장합니다. 이제 PDF에는 우리가 만든 북마크가 포함됩니다.

## 결론

Aspose.Words for .NET을 사용하여 Word 문서에 북마크를 만드는 것은 간단하고 문서 탐색 및 구성에 매우 유용합니다. 보고서를 생성하든, eBook을 만들든, 대용량 문서를 관리하든 북마크를 사용하면 작업이 더 쉬워집니다. 이 튜토리얼에 설명된 단계를 따르면 북마크된 PDF가 즉시 준비됩니다.

## FAQ

### 다양한 수준에서 여러 북마크를 만들 수 있나요?

전적으로! 문서를 PDF로 저장할 때 필요한 만큼 책갈피를 만들고 계층 수준을 정의할 수 있습니다.

### 북마크의 텍스트를 어떻게 업데이트하나요?

 다음을 사용하여 북마크로 이동할 수 있습니다.`DocumentBuilder.MoveToBookmark` 그런 다음 텍스트를 업데이트합니다.

### 북마크 삭제가 가능한가요?

 예, 다음을 사용하여 북마크를 삭제할 수 있습니다.`Bookmarks.Remove` 북마크의 이름을 지정하여 방법을 수행합니다.

### PDF 외에 다른 형식으로 북마크를 만들 수 있나요?

예, Aspose.Words는 DOCX, HTML, EPUB를 포함한 다양한 형식의 북마크를 지원합니다.

### 북마크가 PDF에 올바르게 표시되는지 어떻게 확인할 수 있나요?

 다음을 반드시 정의하세요.`BookmarksOutlineLevels` 제대로`PdfSaveOptions`. 이렇게 하면 책갈피가 PDF 개요에 포함됩니다.