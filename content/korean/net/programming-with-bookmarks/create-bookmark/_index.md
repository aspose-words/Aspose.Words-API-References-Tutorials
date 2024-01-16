---
title: Word 문서에 북마크 만들기
linktitle: Word 문서에 북마크 만들기
second_title: Aspose.Words 문서 처리 API
description: Word 문서에서 북마크를 생성하고 Aspose.Words for .NET을 사용하여 PDF에서 북마크 미리 보기 수준을 지정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/create-bookmark/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 .NET용 Aspose.Words 라이브러리에서 Create Bookmark 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 문서에 책갈피를 만들고 출력 PDF 파일에 책갈피 미리 보기 수준을 지정할 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 문서 및 생성기 만들기

 북마크를 만들기 전에 다음을 사용하여 문서와 문서 빌더를 만들어야 합니다.`Document` 그리고`DocumentBuilder` 사물:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 기본 북마크 만들기

 우리는`StartBookmark` 기본 북마크를 시작하는 방법과`EndBookmark` 끝내는 방법. 그 사이에 텍스트와 기타 북마크를 추가할 수 있습니다.

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// 여기에 북마크나 텍스트를 더 추가하세요.

builder. EndBookmark("My Bookmark");
```

## 3단계: 중첩된 책갈피 만들기

기본 책갈피 안에 중첩된 책갈피를 만들 수도 있습니다. 우리는 같은 것을 사용합니다`StartBookmark` 그리고`EndBookmark` 중첩된 책갈피를 만들고 종료하는 방법:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## 4단계: 출력 PDF 파일에서 북마크 미리보기 수준 지정

 우리는`PdfSaveOptions` 출력 PDF 파일에서 책갈피 미리보기 수준을 지정하는 개체입니다. 우리는`BookmarksOutlineLevels` 재산

  기본 책갈피와 중첩된 책갈피를 해당 수준에 추가하려면 다음을 수행하세요.

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### .NET용 Aspose.Words를 사용하여 북마크 만들기에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 북마크를 만드는 방법을 보여주는 전체 예제 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## 결론

이 기사에서는 .NET용 Aspose.Words의 북마크 만들기 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 우리는 문서에 북마크를 생성하고 출력 PDF 파일에 북마크 미리 보기 수준을 지정하는 단계별 가이드를 따랐습니다.

### 자주 묻는 질문

#### Q: Aspose.Words for .NET에서 "북마크 만들기" 기능을 사용하기 위한 전제 조건은 무엇입니까?

A: Aspose.Words for .NET의 "북마크 만들기" 기능을 사용하려면 C# 언어에 대한 기본 지식이 있어야 합니다. 또한 Aspose.Words 라이브러리가 설치된 .NET 개발 환경이 필요합니다.

#### Q: .NET용 Aspose.Words에서 문서를 만드는 방법은 무엇입니까?

 A: .NET용 Aspose.Words에서 문서를 생성하려면 다음을 사용할 수 있습니다.`Document` 수업. 다음은 샘플 코드입니다.

```csharp
Document doc = new Document();
```

#### Q: .NET용 Aspose.Words를 사용하여 문서에 마스터 북마크를 만드는 방법은 무엇입니까?

 A: .NET용 Aspose.Words를 사용하여 문서에 기본 책갈피를 만들려면 다음을 사용할 수 있습니다.`StartBookmark` 북마크를 시작하고 그 안에 텍스트나 기타 북마크를 추가한 다음` EndBookmark` 그것을 끝내기 위해. 다음은 샘플 코드입니다.

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q: Aspose.Words for .NET을 사용하여 기본 책갈피 안에 중첩된 책갈피를 만드는 방법은 무엇입니까?

 A: Aspose.Words for .NET을 사용하여 기본 책갈피 안에 중첩된 책갈피를 만들려면 동일한 방법을 사용할 수 있습니다.`StartBookmark` 그리고`EndBookmark` 중첩된 북마크를 시작하고 종료하는 메서드입니다. 다음은 샘플 코드입니다.

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Q: .NET용 Aspose.Words를 사용하여 출력 PDF에서 북마크 미리보기 수준을 지정하는 방법은 무엇입니까?

 A: .NET용 Aspose.Words를 사용하여 출력 PDF에서 북마크 미리보기 수준을 지정하려면 다음을 사용할 수 있습니다.`PdfSaveOptions` 수업과`BookmarksOutlineLevels` 재산. 각 수준에 따라 기본 책갈피와 중첩 책갈피를 추가할 수 있습니다. 다음은 샘플 코드입니다.

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Q: Aspose.Words for .NET을 사용하여 북마크를 생성한 후 문서를 저장하는 방법은 무엇입니까?

 A: Aspose.Words for .NET을 사용하여 북마크를 생성한 후 문서를 저장하려면`Save` 의 방법`Document` 대상 파일 경로를 지정하는 객체입니다. 다음은 샘플 코드입니다.

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Q: .NET용 Aspose.Words를 사용하여 출력 PDF에서 북마크 미리보기 수준을 지정하는 방법은 무엇입니까?

 A: .NET용 Aspose.Words를 사용하여 출력 PDF에서 북마크 미리보기 수준을 지정하려면 다음을 사용할 수 있습니다.`PdfSaveOptions` 수업과`BookmarksOutlineLevels` 재산. 각 수준에 따라 기본 책갈피와 중첩 책갈피를 추가할 수 있습니다. 다음은 샘플 코드입니다.

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Q: Aspose.Words for .NET을 사용하여 기본 책갈피 안에 중첩된 책갈피를 만드는 방법은 무엇입니까?

 A: Aspose.Words for .NET을 사용하여 기본 책갈피 안에 중첩된 책갈피를 만들려면 동일한 방법을 사용할 수 있습니다.`StartBookmark` 그리고`EndBookmark` 중첩된 북마크를 시작하고 종료하는 방법. 호출 시 상위 북마크를 매개변수로 지정해야 합니다.`StartBookmark` 방법. 다음은 샘플 코드입니다.

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### Q: .NET용 Aspose.Words를 사용하여 책갈피 안에 텍스트를 추가하는 방법은 무엇입니까?

 A: .NET용 Aspose.Words를 사용하여 책갈피 안에 텍스트를 추가하려면 다음을 사용할 수 있습니다.`Write` 의 방법`DocumentBuilder`추가할 텍스트를 지정하는 개체입니다. 다음은 샘플 코드입니다.

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q: .NET용 Aspose.Words를 사용하여 문서에 마스터 북마크를 만드는 방법은 무엇입니까?

 A: .NET용 Aspose.Words를 사용하여 문서에 기본 책갈피를 만들려면 다음을 사용할 수 있습니다.`StartBookmark` 북마크를 시작하는 방법과`EndBookmark` 끝내는 방법. 다음은 샘플 코드입니다.

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```