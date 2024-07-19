---
title: HTML에서 테이블 삽입
linktitle: HTML에서 테이블 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 HTML의 표를 Word 문서에 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/insert-table-from-html/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 HTML에서 Word 문서에 표를 삽입하는 방법을 배웁니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 HTML의 테이블을 Word 문서에 삽입할 수 있게 됩니다.

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

## 3단계: HTML에서 테이블 삽입
다음으로 HTML 코드를 사용하여 문서에 테이블을 삽입하겠습니다. 다음 코드를 사용하세요.

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 여기서 우리는`InsertHtml` 테이블이 포함된 HTML을 삽입하는 문서 작성기의 메소드입니다. 지정된 HTML은 각 행에 두 개의 행과 두 개의 셀이 있는 테이블을 만듭니다. 필요에 따라 HTML 코드를 수정하여 테이블의 내용을 사용자 정의할 수 있습니다.

## 4단계: 수정된 문서 저장
마지막으로 HTML에서 삽입된 테이블과 함께 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 HTML에서 테이블 삽입에 대한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// AutoFitSettings는 HTML에서 삽입된 테이블에는 적용되지 않습니다.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 HTML에서 Word 문서에 표를 삽입하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 프로그래밍 방식으로 HTML의 테이블을 Word 문서에 삽입할 수 있습니다. 이 기능을 사용하면 HTML 소스의 표 형식 데이터를 Word 문서로 변환하고 가져올 수 있습니다.
