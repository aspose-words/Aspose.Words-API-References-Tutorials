---
title: 테이블 직접 삽입
linktitle: 테이블 직접 삽입
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에 표를 직접 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/insert-table-directly/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 표를 직접 삽입하는 방법을 알아봅니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서에 직접 표를 삽입할 수 있게 됩니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 및 표 만들기
배열로 단어 처리를 시작하려면 새 문서를 만들고 배열을 초기화해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서작성
Document doc = new Document();

//배열 만들기
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 어레이 구축
다음으로 행과 셀을 추가하여 테이블을 작성하겠습니다. 다음 코드를 예로 사용하세요.

```csharp
// 첫 번째 행 만들기
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// 첫 번째 셀 만들기
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// 행의 두 번째 셀에 대한 셀을 복제합니다.
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 여기서는 다음과 같은 행을 만듭니다.`AllowBreakAcrossPages` 다음으로 설정된 속성`true` 행 사이에 페이지 나누기를 허용합니다. 그런 다음 배경색이 지정되고 너비가 고정되고 텍스트 내용이 지정된 셀을 만듭니다. 그런 다음 이 셀을 복제하여 행의 두 번째 셀을 만듭니다.

## 4단계: 테이블 자동 맞춤
테이블의 형식을 올바르게 지정하기 위해 자동 조정을 테이블에 적용할 수 있습니다. 다음 코드를 사용하세요.

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

이 코드 줄은 고정된 열 너비를 기준으로 자동 맞춤을 적용합니다.

## 5단계: 등록

  수정된 문서
마지막으로 테이블을 직접 삽입하여 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 테이블 직접 삽입의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// 테이블 객체를 생성하는 것부터 시작합니다. 문서 객체를 전달해야 합니다.
	//각 노드의 생성자에. 이는 우리가 생성하는 모든 노드가 속해야 하기 때문입니다.
	// 어떤 문서에.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// 여기서 EnacheMinimum을 호출하여 행과 셀을 생성할 수 있습니다. 이 방법이 사용됩니다
	// 지정된 노드가 유효한지 확인합니다. 이 경우 유효한 테이블에는 최소한 하나의 행과 하나의 셀이 있어야 합니다.
	// 대신 행과 테이블 생성을 직접 처리하겠습니다.
	// 알고리즘 내부에 테이블을 생성하는 경우 이것이 가장 좋은 방법입니다.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// 이제 자동 맞춤 설정을 적용할 수 있습니다.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// 그런 다음 테이블의 다른 셀과 행에 대해 프로세스를 반복합니다.
	// 기존 셀과 행을 복제하여 작업 속도를 높일 수도 있습니다.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 표를 직접 삽입하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 프로그래밍 방식으로 Word 문서에 테이블을 직접 삽입할 수 있습니다. 이 기능을 사용하면 특정 요구 사항에 따라 테이블을 만들고 사용자 지정할 수 있습니다.