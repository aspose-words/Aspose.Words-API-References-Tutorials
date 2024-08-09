---
title: 행 형식 페이지 나누기 비활성화
linktitle: 행 형식 페이지 나누기 비활성화
second_title: Aspose.Words 문서 처리 API
description: 테이블 가독성과 서식을 유지하기 위해 .NET용 Aspose.Words를 사용하여 Word 문서의 여러 페이지에서 행 나누기를 비활성화하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/row-format-disable-break-across-pages/
---
## 소개

Word 문서에서 표 작업을 할 때 행이 여러 페이지에 걸쳐 나누어지지 않도록 하고 싶을 수 있습니다. 이는 문서의 가독성과 서식을 유지하는 데 필수적일 수 있습니다. Aspose.Words for .NET은 페이지 전체에서 행 나누기를 비활성화하는 쉬운 방법을 제공합니다.

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서의 여러 페이지에서 행 나누기를 비활성화하는 과정을 안내합니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- 여러 페이지에 걸쳐 있는 표가 포함된 Word 문서입니다.

## 네임스페이스 가져오기

먼저 프로젝트에 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## 1단계: 문서 로드

여러 페이지에 걸쳐 있는 테이블이 포함된 문서를 로드합니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## 2단계: 테이블에 액세스

문서의 첫 번째 테이블에 액세스합니다. 여기서는 수정하려는 테이블이 문서의 첫 번째 테이블이라고 가정합니다.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## 3단계: 모든 행에 대해 페이지 나누기 비활성화

 테이블의 각 행을 반복하고 다음을 설정합니다.`AllowBreakAcrossPages`재산`false`. 이렇게 하면 행이 여러 페이지에 걸쳐 나누어지지 않습니다.

```csharp
// 테이블의 모든 행에 대해 페이지 나누기를 비활성화합니다.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## 4단계: 문서 저장

수정된 문서를 지정된 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 페이지 전체에서 행 나누기를 비활성화하는 방법을 시연했습니다. 위에 설명된 단계를 수행하면 표 행이 그대로 유지되고 페이지에 걸쳐 분할되지 않고 문서의 가독성과 서식이 유지되도록 할 수 있습니다.

## FAQ

### 모든 행 대신 특정 행에 대해 페이지 전체에서 행 나누기를 비활성화할 수 있나요?  
 예, 원하는 행에 액세스하고 해당 행을 설정하여 특정 행에 대한 행 나누기를 비활성화할 수 있습니다.`AllowBreakAcrossPages`재산`false`.

### 이 방법은 병합된 셀이 있는 테이블에 작동합니까?  
 예, 이 방법은 병합된 셀이 있는 테이블에 작동합니다. 부동산`AllowBreakAcrossPages` 셀 병합에 관계없이 전체 행에 적용됩니다.

### 테이블이 다른 테이블 안에 중첩되어 있는 경우 이 방법이 작동합니까?  
예, 동일한 방식으로 중첩 테이블에 액세스하고 수정할 수 있습니다. 인덱스나 기타 속성을 통해 중첩 테이블을 올바르게 참조하는지 확인하세요.

### 행이 페이지 분할을 허용하는지 어떻게 확인할 수 있나요?  
 행에 액세스하여 페이지 분할을 허용하는지 확인할 수 있습니다.`AllowBreakAcrossPages` 의 재산`RowFormat` 그리고 그 가치를 확인합니다.

### 문서의 모든 테이블에 이 설정을 적용할 수 있는 방법이 있나요?  
예, 문서의 모든 테이블을 반복하여 각 테이블에 이 설정을 적용할 수 있습니다.