---
title: 수평 병합
linktitle: 수평 병합
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 테이블의 셀을 수평으로 병합하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/horizontal-merge/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 표에 있는 셀을 수평으로 병합하는 방법을 알아봅니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 표의 셀을 수평으로 병합할 수 있게 됩니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 생성 및 문서 생성기 초기화
테이블과 셀로 단어 처리를 시작하려면 새 문서를 만들고 문서 생성기를 초기화해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//문서 생성 및 문서 생성기 초기화
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 셀을 수평으로 병합하여 테이블 작성
다음으로, Aspose.Words for .NET에서 제공하는 속성을 사용하여 테이블을 작성하고 수평 셀 병합을 적용하겠습니다. 다음 코드를 사용하세요.

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// 이 셀은 이전 셀과 병합되므로 비어 있어야 합니다.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 여기서는 문서 작성기를 사용하여 테이블을 작성하고 셀 수평 병합 속성을 설정합니다. 우리는`HorizontalMerge` 의 재산`CellFormat` 각 셀에 적용할 수평 병합 유형을 지정하는 개체입니다. 사용`CellMerge.First` 사용하는 동안 첫 번째 셀을 다음 셀과 병합합니다.`CellMerge.Previous` 현재 셀을 이전 셀과 병합합니다.`CellMerge.None` 셀이 병합되지 않아야 함을 나타냅니다.

## 4단계: 수정된 문서 저장
마지막으로 셀이 수평으로 병합된 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 수평 병합의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// 이 셀은 이전 셀과 병합되므로 비어 있어야 합니다.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 표에 있는 셀을 수평으로 병합하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 표에 프로그래밍 방식으로 가로 셀 병합을 적용할 수 있습니다. 이 기능을 사용하면 더 복잡한 테이블 레이아웃을 만들고 데이터를 더 잘 구성할 수 있습니다.