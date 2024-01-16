---
title: Word 문서의 책갈피 테이블 열
linktitle: Word 문서의 책갈피 테이블 열
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 표 열을 북마크하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/bookmark-table-columns/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 Aspose.Words for .NET 라이브러리에서 Bookmark Table Columns 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 Word 문서에 있는 표의 특정 열을 북마크하고 해당 열의 내용에 액세스할 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 테이블 생성

 테이블 열에 북마크를 생성하기 전에 먼저 테이블을 생성해야 합니다.`DocumentBuilder`물체. 이 예에서는 두 개의 행과 두 개의 열이 있는 테이블을 만듭니다.

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## 2단계: 열 북마크 만들기

 우리는`StartBookmark` 테이블의 특정 열에 책갈피를 만드는 방법입니다. 이 예에서는 북마크에 "MyBookmark"라는 이름을 사용합니다.

```csharp
builder. StartBookmark("MyBookmark");
```

## 3단계: 열 콘텐츠에 액세스

 문서의 모든 북마크를 살펴보고 해당 이름을 표시합니다. 북마크가 열인 경우 열 인덱스와`GetText` 방법:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### .NET용 Aspose.Words를 사용하는 북마크 테이블 열의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 테이블 열에 책갈피를 만드는 방법을 보여주는 전체 샘플 소스 코드입니다.

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## 결론

이 기사에서는 Aspose.Words for .NET의 Bookmark Table Columns 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 우리는 Word 문서에서 표의 특정 열을 북마크에 추가하고 해당 열의 내용으로 이동하는 단계별 지침을 따랐습니다.

### Word 문서의 북마크 테이블 열에 대한 FAQ

#### Q: Aspose.Words for .NET에서 "테이블 열에 대한 북마크" 기능을 사용하기 위한 전제 조건은 무엇입니까?

A: Aspose.Words for .NET의 "테이블 열에 대한 북마크" 기능을 사용하려면 C# 언어에 대한 기본 지식이 필요합니다. 또한 Aspose.Words 라이브러리가 설치된 .NET 개발 환경이 필요합니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 열이 포함된 테이블을 만드는 방법은 무엇입니까?

 A: .NET용 Aspose.Words를 사용하여 Word 문서에 열이 있는 테이블을 만들려면 다음을 사용할 수 있습니다.`DocumentBuilder` 테이블에 셀과 내용을 삽입하는 개체입니다. 다음은 샘플 코드입니다.

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### Q: Aspose.Words for .NET을 사용하여 테이블 열을 북마크하는 방법은 무엇입니까?

 A: Aspose.Words for .NET을 사용하여 테이블 열에 책갈피를 생성하려면 다음을 사용할 수 있습니다.`StartBookmark` 의 방법`DocumentBuilder` 특정 테이블 열에서 책갈피를 시작하는 개체입니다. 다음은 샘플 코드입니다.

```csharp
builder.StartBookmark("MyBookmark");
```

#### Q: .NET용 Aspose.Words를 사용하여 북마크에서 테이블 열 콘텐츠에 액세스하는 방법은 무엇입니까?

A: Aspose.Words for .NET을 사용하여 책갈피에서 테이블 열의 내용에 액세스하려면 문서의 모든 책갈피를 반복하고 책갈피가 열인지 확인한 다음 열의 인덱스를 사용하여 그 칼럼. 다음은 샘플 코드입니다.

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // 칼럼의 내용으로 뭔가를 하세요...
         }
     }
}
```

#### Q: 열 책갈피가 있는 테이블에서 생성할 수 있는 열 수에 제한이 있습니까?

A: Aspose.Words for .NET을 사용하여 열 책갈피가 있는 테이블에서 생성할 수 있는 열 수에는 특별한 제한이 없습니다. 제한은 주로 시스템에서 사용 가능한 리소스와 사용 중인 Word 파일 형식의 사양에 따라 달라집니다. 그러나 너무 많은 수의 열을 생성하지 않는 것이 좋습니다. 이는 최종 문서의 성능과 가독성에 영향을 미칠 수 있습니다.