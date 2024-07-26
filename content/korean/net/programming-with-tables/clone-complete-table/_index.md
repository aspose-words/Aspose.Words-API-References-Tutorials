---
title: 전체 테이블 복제
linktitle: 전체 테이블 복제
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 전체 테이블을 Word 문서로 복제하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/clone-complete-table/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 전체 테이블을 Word 문서로 복제하는 방법을 배웁니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 테이블을 Word 문서에 복제할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드 및 테이블 액세스
테이블로 단어 처리를 시작하려면 해당 테이블이 포함된 문서를 로드하고 액세스해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Tables.docx");

// 어레이에 대한 액세스
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 전체 어레이 복제
다음으로 전체 테이블을 복제하여 원본 뒤에 문서에 삽입하겠습니다. 다음 코드를 사용하세요.

```csharp
// 어레이 복제
Table tableClone = (Table)table.Clone(true);

// 원본 테이블 뒤에 복제된 테이블을 문서에 삽입합니다.
table.ParentNode.InsertAfter(tableClone, table);

// 두 테이블 사이에 빈 단락 삽입
// 그렇지 않으면 저장 시 하나로 결합됩니다(이는 문서 유효성 검사 때문입니다).
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 여기서 우리는`Clone` 배열의 전체 복사본을 만드는 방법입니다. 그런 다음 우리는`InsertAfter` 원본 테이블 뒤에 복제된 테이블을 문서에 삽입합니다. 또한 저장할 때 병합되는 것을 방지하기 위해 두 테이블 사이에 빈 단락을 추가합니다.

## 4단계: 수정된 문서 저장
마지막으로 복제된 테이블과 함께 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
// 수정된 문서를 저장하세요
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.
  
### .NET용 Aspose.Words를 사용하는 Clone Complete Table의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// 테이블을 복제하여 원본 뒤에 문서에 삽입합니다.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// 두 테이블 사이에 빈 단락을 삽입하고,
	// 그렇지 않으면 저장 시 하나로 결합됩니다. 이는 문서 유효성 검사와 관련이 있습니다.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 전체 테이블을 Word 문서로 복제하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서의 테이블을 프로그래밍 방식으로 복제할 수 있습니다. 이 기능을 사용하면 특정 요구 사항에 맞게 어레이에 대한 고급 조작을 수행할 수 있습니다.