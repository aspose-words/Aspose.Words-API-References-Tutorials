---
title: 수직 병합
linktitle: 수직 병합
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 표에 있는 셀을 수직으로 병합하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/vertical-merge/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 표에 있는 셀을 수직으로 병합하는 방법을 알아봅니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 Word 문서의 표에 있는 셀을 수직으로 병합할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드
문서에서 단어 처리를 시작하려면 다음 단계를 따르세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 새 문서 만들기
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 셀을 수직으로 병합
다음으로 테이블의 세로 셀을 병합하겠습니다. 다음 코드를 사용하세요.

```csharp
// 셀 삽입
builder. InsertCell();

// 첫 번째 셀에 수직 병합 적용
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// 다른 셀 삽입
builder. InsertCell();

// 셀에 수직 병합을 적용하지 않습니다.
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// 셀 삽입
builder. InsertCell();

// 이전 셀과 수직 병합 적용
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// 다른 셀 삽입
builder. InsertCell();

// 셀에 수직 병합을 적용하지 않습니다.
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//테이블 생성 종료
builder. EndTable();
```

이 코드에서는 DocumentBuilder 생성자를 사용하여 테이블에 셀을 삽입합니다. CellFormat.VerticalMerge 속성을 사용하여 셀에 수직 병합을 적용합니다. 첫 번째 셀 병합에는 CellMerge.First를 사용하고, 이전 셀과 병합하려면 CellMerge.Previous를 사용하며, 수직 병합이 없는 경우에는 CellMerge.None을 사용합니다.

## 4단계: 수정된 문서 저장
마지막으로, 병합된 셀과 함께 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용한 수직 병합의 샘플 소스 코드 
```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// 이 셀은 위의 셀에 수직으로 병합되므로 비어 있어야 합니다.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 표에 있는 셀을 수직으로 병합하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 테이블의 세로 셀을 쉽게 병합할 수 있습니다.