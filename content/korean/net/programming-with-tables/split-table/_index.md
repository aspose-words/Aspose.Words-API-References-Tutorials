---
title: 테이블 분할
linktitle: 테이블 분할
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 테이블을 분할하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/split-table/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블을 분할하는 방법을 배우겠습니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 Word 문서의 특정 행에서 테이블을 분할할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드
문서에서 단어 처리를 시작하려면 다음 단계를 따르세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Tables.docx");
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸고 올바른 파일 이름을 제공하십시오.

## 3단계: 테이블 나누기
다음으로 특정 행에서 테이블을 분할합니다. 다음 코드를 사용하세요.

```csharp
// 첫 번째 테이블 검색
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// 테이블을 나눌 선 결정
Row row = firstTable.Rows[2];

// 분할 테이블을 위한 새 컨테이너 만들기
Table table = (Table)firstTable.Clone(false);

// 원래 테이블 뒤에 컨테이너를 삽입합니다.
firstTable.ParentNode.InsertAfter(table, firstTable);

// 테이블 사이의 거리를 유지하기 위해 버퍼 단락을 추가하세요.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// 원본 테이블의 행을 분할 테이블로 이동
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

여기서는 문서를 사용하여 문서 노드에서 첫 번째 테이블을 검색합니다. 그런 다음 테이블을 분할할 행을 결정합니다. 이 예에서는 세 번째 행(인덱스 2)입니다. 그런 다음 원본 테이블을 복제하여 새 컨테이너를 만든 다음 원본 테이블 뒤에 삽입합니다. 또한 두 테이블 사이의 거리를 유지하기 위해 버퍼 단락을 추가합니다. 그런 다음 지정된 행에 도달할 때까지 do-while 루프를 사용하여 원래 테이블의 행을 분할 테이블로 이동합니다.

## 4단계: 수정된 문서 저장
마지막으로 저장해야 할 것은

  분할 테이블로 수정된 문서입니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 분할 테이블의 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// 세 번째 행(포함)에서 테이블을 분할합니다.
Row row = firstTable.Rows[2];
// 분할 테이블에 대한 새 컨테이너를 만듭니다.
Table table = (Table) firstTable.Clone(false);
// 원본 뒤에 용기를 삽입하세요.
firstTable.ParentNode.InsertAfter(table, firstTable);
// 테이블이 서로 떨어져 있도록 버퍼 단락을 추가하세요.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블을 분할하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서의 특정 줄에서 테이블을 쉽게 분할할 수 있습니다.