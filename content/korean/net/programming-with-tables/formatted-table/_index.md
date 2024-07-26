---
title: 서식이 지정된 테이블
linktitle: 서식이 지정된 테이블
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 서식이 지정된 테이블을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/formatted-table/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 서식이 지정된 테이블을 만드는 방법을 배웁니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서에서 사용자 지정 서식을 사용하여 테이블을 만들 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 생성 및 문서 생성기 초기화
서식이 지정된 테이블 작성을 시작하려면 새 문서를 만들고 문서 생성기를 초기화해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//문서 생성 및 문서 생성기 초기화
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 서식이 지정된 테이블 작성
다음으로 문서 작성기에서 제공하는 방법을 사용하여 서식이 지정된 테이블을 작성하겠습니다. 다음 코드를 사용하세요.

```csharp
// 어레이 구성 시작
Table table = builder. StartTable();

// 테이블 헤더 행 구성
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// 어레이 본체의 구성
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// 어레이 구성 종료
builder. EndTable();
```

 여기서는 문서 작성기를 사용하여 테이블을 단계별로 작성합니다. 우리는 전화부터 시작합니다`StartTable()` 테이블을 초기화합니다. 그런 다음 우리는`InsertCell()` 셀을 삽입하고`Write()` 각 셀에 내용을 추가합니다. 또한 다양한 서식 속성을 사용하여 테이블 행, 셀 및 텍스트의 서식을 정의합니다.

## 4단계: 문서 저장
마지막으로 서식이 지정된 테이블이 포함된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
// 문서 저장
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 형식화된 테이블의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// 테이블 전체 서식은 테이블에 행이 하나 이상 존재한 후에 적용되어야 합니다.
	table.LeftIndent = 20.0;
	// 높이를 설정하고 머리글 행의 높이 규칙을 정의합니다.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// 이 셀의 너비는 이전 셀에서 상속되므로 지정할 필요가 없습니다.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// 높이를 재설정하고 테이블 본체에 대해 다른 높이 규칙을 정의합니다.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// 글꼴 서식을 재설정합니다.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 서식이 지정된 테이블을 만드는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서에서 특정 서식을 사용하여 프로그래밍 방식으로 사용자 지정 테이블을 만들 수 있습니다. 이 기능을 사용하면 시각적으로 매력적이고 체계적인 방식으로 데이터를 표시하고 구조화할 수 있습니다.