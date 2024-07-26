---
title: 간단한 테이블 만들기
linktitle: 간단한 테이블 만들기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 간단한 테이블을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/create-simple-table/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 간단한 테이블을 만드는 방법을 배우겠습니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서에 사용자 정의 테이블을 만들 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 생성 및 문서 생성기 초기화
테이블 작성을 시작하려면 새 문서를 만들고 문서 작성기를 초기화해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//문서 생성 및 문서 생성기 초기화
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 어레이 구축
다음으로 문서 작성기에서 제공하는 방법을 사용하여 테이블을 작성하겠습니다. 다음 코드를 사용하세요.

```csharp
// 어레이 구성 시작
builder. StartTable();

// 첫 번째 행의 첫 번째 셀 구성
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// 첫 번째 행의 두 번째 셀 구성
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

// 첫 번째 줄을 끝내고 새 줄을 시작하려면 다음 메서드를 호출하세요.
builder. EndRow();

// 두 번째 행의 첫 번째 셀 구성
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// 두 번째 행의 두 번째 셀 구성
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// 두 번째 줄을 끝내려면 다음 메서드를 호출하세요.
builder. EndRow();

// 테이블 구성이 완료되었음을 나타냅니다.
builder. EndTable();
```

 여기서는 문서 작성기를 사용하여 테이블을 단계별로 작성합니다. 우리는 전화부터 시작합니다`StartTable()` 테이블을 초기화하고 다음을 사용하십시오.`InsertCell()` 셀을 삽입하고`Write()` 각 셀에 내용을 추가합니다. 우리는 또한 사용합니다`EndRow()` 행을 끝내고 새 행을 시작하려면 마지막으로, 우리는 전화`EndTable()` 테이블 구성이 완료되었음을 나타냅니다.

## 4단계: 문서 저장
마지막으로 저장해야합니다.

  생성된 테이블이 있는 문서입니다. 다음 코드를 사용하세요.

```csharp
// 문서 저장
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 간단한 테이블 만들기의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// 테이블 만들기를 시작하세요.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// 두 번째 셀을 만듭니다.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// 행을 종료하고 새 행을 시작하려면 다음 메서드를 호출합니다.
	builder.EndRow();
	// 두 번째 행의 첫 번째 셀을 만듭니다.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// 두 번째 셀을 만듭니다.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	// 테이블 구축이 완료되었음을 알리는 신호입니다.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 간단한 테이블을 만드는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서에서 프로그래밍 방식으로 사용자 지정 테이블을 만들 수 있습니다. 이 기능을 사용하면 구조적이고 명확한 방식으로 데이터의 형식을 지정하고 구성할 수 있습니다.