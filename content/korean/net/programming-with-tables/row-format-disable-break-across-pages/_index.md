---
title: 행 형식 페이지 나누기 비활성화
linktitle: 행 형식 페이지 나누기 비활성화
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 여러 페이지에 걸쳐 표에 대한 줄 바꿈을 비활성화하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/row-format-disable-break-across-pages/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 여러 페이지로 구성된 표의 줄바꿈을 비활성화하는 방법을 배우겠습니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 Word 문서의 표에 있는 모든 행에 대해 줄바꿈을 비활성화할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드
문서에서 단어 처리를 시작하려면 다음 단계를 따르세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸고 올바른 파일 이름을 제공하십시오.

## 3단계: 테이블 행 나누기 비활성화
다음으로, 테이블의 모든 행에 대해 행 분리를 비활성화하겠습니다. 다음 코드를 사용하세요.

```csharp
// 테이블 검색
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// 테이블의 모든 행에 대해 행 나누기를 비활성화합니다.
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 여기서는 문서를 사용하여 첫 번째 테이블을 가져온 다음 foreach 루프를 사용하여 테이블의 모든 행을 반복합니다. 루프 내에서 다음을 설정하여 각 행에 대한 행 분리를 비활성화합니다.`RowFormat.AllowBreakAcrossPages`재산`false`.

## 4단계: 수정된 문서 저장
마지막으로, 테이블 줄 바꿈을 비활성화한 상태로 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 페이지 간 중단을 비활성화하는 행 형식의 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// 테이블의 모든 행에 대해 페이지 나누기를 비활성화합니다.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 다중 페이지 표의 줄 바꿈을 비활성화하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서의 테이블에 이 비활성화를 적용할 수 있습니다.