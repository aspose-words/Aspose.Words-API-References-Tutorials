---
title: 기본 너비 유형 검색
linktitle: 기본 너비 유형 검색
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 테이블에서 셀의 유형 및 기본 너비 값을 검색하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/retrieve-preferred-width-type/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 테이블 셀에서 기본 너비 유형과 해당 값을 검색하는 방법을 알아봅니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 Word 문서 테이블의 특정 셀에 대해 선호하는 너비 유형(절대, 상대 또는 자동)과 해당 값을 검색할 수 있습니다.

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

## 3단계: 선호하는 너비 유형 및 값 검색
다음으로 특정 테이블 셀에 대해 선호하는 너비 유형과 해당 값을 검색합니다. 다음 코드를 사용하세요.

```csharp
// 테이블 검색
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// 자동 테이블 조정 활성화
table. AllowAutoFit = true;

//첫 번째 행의 첫 번째 셀을 검색합니다.
Cell firstCell = table.FirstRow.FirstCell;

// 선호하는 너비 유형과 해당 값을 검색합니다.
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 여기서는 문서를 사용하여 첫 번째 테이블을 가져온 다음 자동 테이블 맞춤을 활성화합니다.`AllowAutoFit` 재산. 그런 다음 테이블의 첫 번째 행의 첫 번째 셀을 검색합니다. 이 셀에서 다음을 사용하여 선호하는 너비 유형을 검색할 수 있습니다.`PreferredWidth.Type` 재산과 그 가치`PreferredWidth.Value` 재산.

### .NET용 Aspose.Words를 사용하여 기본 너비 유형 검색에 대한 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 테이블 셀에서 기본 너비 유형과 해당 값을 검색하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서 테이블의 특정 셀에 대한 이 정보를 검색할 수 있습니다.