---
title: 행 형식 페이지 간 나누기 비활성화
linktitle: 행 형식 페이지 간 나누기 비활성화
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서의 여러 페이지에서 행 나누기를 비활성화하여 표의 가독성과 서식을 유지하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/row-format-disable-break-across-pages/
---
## 소개

Word 문서에서 표로 작업할 때 행이 여러 페이지로 나뉘지 않도록 해야 할 수 있습니다. 이는 문서의 가독성과 서식을 유지하는 데 필수적일 수 있습니다. Aspose.Words for .NET은 여러 페이지에서 행 나누기를 비활성화하는 간편한 방법을 제공합니다.

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 여러 페이지에서 행 나누기를 비활성화하는 과정을 안내해 드리겠습니다.

## 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.
- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- 여러 페이지에 걸쳐 표가 있는 Word 문서입니다.

## 네임스페이스 가져오기

먼저 프로젝트에 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## 1단계: 문서 로드

여러 페이지에 걸쳐 있는 표가 포함된 문서를 로드합니다.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## 2단계: 테이블에 접근하기

문서의 첫 번째 테이블에 액세스합니다. 이는 수정하려는 테이블이 문서의 첫 번째 테이블이라고 가정합니다.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## 3단계: 모든 행에 대한 페이지 간 나누기 비활성화

 표의 각 행을 반복하고 설정하십시오.`AllowBreakAcrossPages`재산에`false`이렇게 하면 행이 여러 페이지로 나눠지지 않습니다.

```csharp
// 표의 모든 행에 대해 페이지 넘기기 기능을 비활성화합니다.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## 4단계: 문서 저장

수정된 문서를 지정된 디렉토리에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 페이지 간에 행 나누기를 비활성화하는 방법을 보여주었습니다. 위에 설명된 단계를 따르면 테이블 행이 그대로 유지되고 페이지에 걸쳐 분할되지 않아 문서의 가독성과 서식을 유지할 수 있습니다.

## 자주 묻는 질문

### 모든 행이 아닌 특정 행에 대해서만 페이지 간 행 나누기를 비활성화할 수 있나요?  
 예, 원하는 행에 액세스하고 해당 행을 설정하여 특정 행에 대한 행 나누기를 비활성화할 수 있습니다.`AllowBreakAcrossPages`재산에`false`.

### 이 방법은 셀이 병합된 표에도 적용되나요?  
 예, 이 방법은 병합된 셀이 있는 표에 적용됩니다. 속성`AllowBreakAcrossPages` 셀 병합과 관계없이 전체 행에 적용됩니다.

### 테이블이 다른 테이블 안에 중첩되어 있는 경우에도 이 방법이 효과가 있을까요?  
네, 같은 방식으로 중첩된 테이블에 액세스하고 수정할 수 있습니다. 중첩된 테이블을 인덱스나 다른 속성으로 올바르게 참조해야 합니다.

### 행이 페이지 간 변경을 허용하는지 어떻게 확인할 수 있나요?  
 행이 페이지 간 분할을 허용하는지 확인하려면 다음을 수행하세요.`AllowBreakAcrossPages` 의 속성`RowFormat` 그리고 그 가치를 확인합니다.

### 이 설정을 문서의 모든 표에 적용할 방법이 있나요?  
네, 문서의 모든 표를 반복하여 각 표에 이 설정을 적용할 수 있습니다.