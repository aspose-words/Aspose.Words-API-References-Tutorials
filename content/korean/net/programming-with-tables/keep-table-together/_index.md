---
title: 테이블을 함께 유지
linktitle: 테이블을 함께 유지
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에서 테이블을 함께 유지하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/keep-table-together/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블을 함께 유지하는 방법을 배우겠습니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 표가 Word 문서의 여러 페이지에 걸쳐 분할되지 않고 그대로 유지될 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드 및 테이블 검색
테이블로 단어 처리를 시작하려면 문서를 로드하고 함께 보관하려는 테이블을 가져와야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// 테이블 검색
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: "KeepWithNext" 옵션 활성화
테이블을 함께 유지하고 여러 페이지로 분할되는 것을 방지하려면 테이블 마지막 행의 마지막 단락을 제외하고 테이블의 각 단락에 대해 "KeepWithNext" 옵션을 활성화해야 합니다. 다음 코드를 사용하세요.

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

여기서는 테이블의 각 셀을 반복하고 테이블의 마지막 행의 마지막 단락을 제외하고 셀의 각 단락에 대해 "KeepWithNext" 옵션을 활성화합니다.

## 4단계: 수정된 문서 저장
마지막으로 수정된 문서를 테이블과 함께 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 Keep Table Together의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// 페이지 전체에 걸쳐 페이지가 깨지는 것을 방지하려면 테이블의 모든 단락에 대해 KeepWithNext를 활성화해야 합니다.
	//표 마지막 행의 마지막 단락을 제외하고.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블을 함께 유지하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 테이블을 그대로 유지하고 문서의 여러 페이지에 걸쳐 분할되는 것을 방지할 수 있습니다. 이 기능을 사용하면 문서의 표 모양과 레이아웃을 더 세부적으로 제어할 수 있습니다.