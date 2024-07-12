---
title: 후속 페이지에서 행 반복
linktitle: 후속 페이지에서 행 반복
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 다음 페이지에서 표 행을 반복하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 다음 페이지에서 표의 행을 반복하는 방법을 배웁니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 Word 문서 테이블의 다음 페이지에서 반복할 행을 지정할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 생성 및 문서 생성기 초기화
문서 및 문서 생성기로 단어 처리를 시작하려면 다음 단계를 따르십시오.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서작성
Document doc = new Document();

// 문서 생성기 초기화
DocumentBuilder builder = new DocumentBuilder(doc);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 반복되는 행으로 테이블 작성
다음으로, 후속 페이지에 반복되는 행이 있는 테이블을 작성하겠습니다. 다음 코드를 사용하세요.

```csharp
// 테이블의 시작
builder. StartTable();

// 첫 번째 줄 매개변수 구성(헤더 줄)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//첫 번째 행의 첫 번째 셀 삽입
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// 첫 번째 행의 두 번째 셀 삽입
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// 다음 줄의 매개변수를 구성합니다.
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// 다음 행에 셀을 삽입하려면 반복하세요.
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// 테이블 끝
builder. EndTable();
```

 여기서는 문서 작성기를 사용하여 두 개의 머리글 행과 여러 데이터 행이 있는 테이블을 만듭니다. 그만큼`RowFormat.HeadingFormat` 매개변수는 후속 페이지에서 반복되어야 하는 헤더 행을 표시하는 데 사용됩니다.

## 4단계: 수정된 문서 저장
드디어 미국

  테이블의 다음 페이지에 반복되는 헤더 행을 사용하여 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 후속 페이지에서 행 반복을 위한 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 다음 페이지에서 표의 행을 반복하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서에서 특정 요구 사항에 따라 반복할 줄을 지정할 수 있습니다.