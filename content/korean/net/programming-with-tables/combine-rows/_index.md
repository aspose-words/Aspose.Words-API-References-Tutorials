---
title: 행 결합
linktitle: 행 결합
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 테이블 행을 결합하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/combine-rows/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 테이블 행을 결합하는 방법을 배웁니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서의 표 행을 조작하고 병합할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드 및 테이블 액세스
표로 단어 처리를 시작하려면 표가 포함된 문서를 로드하고 액세스해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Tables.docx");

// 테이블에 대한 액세스
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 표 행 결합
다음으로 두 번째 테이블의 행을 첫 번째 테이블의 끝에 결합하겠습니다. 다음 코드를 사용하세요.

```csharp
// 테이블 행의 조합
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 여기서 우리는`while` 루프를 실행하여 두 번째 배열의 모든 행을 반복하고 다음을 사용하여 첫 번째 배열의 끝에 추가합니다.`Add` 방법. 다음으로, 다음을 사용하여 문서에서 두 번째 테이블을 제거합니다.`Remove` 방법.

## 4단계: 수정된 문서 저장
마지막으로, 결합된 테이블 행과 함께 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
// 수정된 문서를 저장하세요
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 행 결합을 위한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// 두 번째 테이블의 행은 첫 번째 테이블의 끝에 추가됩니다.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// 현재 테이블의 모든 행을 다음 테이블에 추가합니다.
	// 셀 수와 너비가 다른 여러 테이블을 하나의 테이블로 합칠 수 있습니다.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블 행을 결합하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서의 표 행을 프로그래밍 방식으로 조작할 수 있습니다. 이 기능을 사용하면 데이터를 테이블로 효율적으로 병합하고 구성할 수 있습니다.