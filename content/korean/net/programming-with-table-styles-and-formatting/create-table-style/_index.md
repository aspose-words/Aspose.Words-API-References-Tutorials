---
title: 테이블 스타일 만들기
linktitle: 테이블 스타일 만들기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 사용자 정의 테이블 스타일을 만드는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/create-table-style/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테이블 스타일을 생성하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 Word 문서의 테이블에 대한 사용자 정의 스타일을 만드는 방법을 알게 됩니다.

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 편집한 Word 문서를 저장하려는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 새 문서 및 문서 작성기 만들기
 다음으로 새 인스턴스를 생성해야 합니다.`Document` 클래스와 해당 문서에 대한 문서 생성자.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 새 표 시작 및 셀 추가
테이블 생성을 시작하려면 다음을 사용합니다.`StartTable()` Document Builder의 메소드를 사용하여 테이블에 셀을 추가합니다.`InsertCell()` 메서드를 사용하여 셀의 내용을 씁니다.`Write()` 방법.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## 4단계: 표 스타일 만들기
 이제 다음을 사용하여 테이블 스타일을 만들 수 있습니다.`TableStyle` 수업과`Add()` 문서의 방법`s `스타일 컬렉션. 테두리, 여백, 패딩과 같은 스타일 속성을 정의합니다.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## 5단계: 표에 표 스타일 적용
 마지막으로, 다음을 사용하여 생성한 테이블 스타일을 테이블에 적용합니다.`Style` 테이블의 속성입니다.

```csharp
table.Style = tableStyle;
```

## 6단계: 수정된 문서 저장
마지막으로 수정된 문서를 파일로 저장합니다. 출력 문서에 대한 적절한 이름과 위치를 선택할 수 있습니다.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 테이블에 대한 사용자 정의 스타일을 만들었습니다.

### .NET용 Aspose.Words를 사용하여 테이블 스타일 만들기의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테이블 스타일을 만드는 방법을 배웠습니다. 이 단계별 가이드를 따르면 Word 문서의 표 스타일을 쉽게 사용자 지정할 수 있습니다. Aspose.Words는 문서의 표를 조작하고 서식을 지정하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 통해 Word 문서의 시각적 표현을 개선하고 특정 요구 사항을 충족할 수 있습니다.