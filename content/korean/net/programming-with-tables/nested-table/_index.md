---
title: 중첩 테이블
linktitle: 중첩 테이블
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 중첩 테이블을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/nested-table/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 중첩 테이블을 만드는 방법을 알아봅니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서에 중첩 테이블을 만들 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 생성 및 문서 생성기 초기화
문서 및 문서 생성기로 단어 처리를 시작하려면 다음 단계를 따르십시오.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 작성
Document doc = new Document();

// 문서 생성기 초기화
DocumentBuilder builder = new DocumentBuilder(doc);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 중첩 테이블 작성
다음으로, 외부 테이블에 셀을 삽입하고 첫 번째 셀 내부에 새 테이블을 생성하여 중첩 테이블을 만듭니다. 다음 코드를 사용하세요.

```csharp
// 외부 테이블의 첫 번째 셀 삽입
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// 외부 테이블의 두 번째 셀 삽입
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// 외부 테이블 종료
builder. EndTable();

// 외부 테이블의 첫 번째 셀로 이동
builder.MoveTo(cell.FirstParagraph);

// 내부 테이블 만들기
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// 내부 테이블 끝
builder. EndTable();
```

여기서는 문서 작성기를 사용하여 셀과 내용을 외부 테이블에 삽입합니다. 그런 다음 문서 작성기 커서를 외부 테이블의 첫 번째 셀로 이동하고 셀과 내용을 삽입하여 내부에 새 테이블을 만듭니다.

## 4단계: 수정된 문서 저장
마지막으로 수정된 문서를 중첩된 테이블과 함께 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

출력 문서의 올바른 경로와 이름 파일을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 중첩 테이블의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// 이 호출은 첫 번째 테이블 내에 중첩 테이블을 만드는 데 중요합니다.
	//이 호출이 없으면 아래에 삽입된 셀이 외부 테이블에 추가됩니다.
	builder.EndTable();
	// 외부 테이블의 첫 번째 셀로 이동합니다.
	builder.MoveTo(cell.FirstParagraph);
	// 내부 테이블을 구축합니다.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 중첩 테이블을 만드는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서의 특정 요구 사항에 따라 프로그래밍 방식으로 중첩 테이블을 만들 수 있습니다.
