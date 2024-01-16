---
title: 스타일로 테이블 만들기
linktitle: 스타일로 테이블 만들기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 사용자 정의 스타일로 테이블을 구축하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 스타일이 지정된 테이블을 구축하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 Word 문서에서 사용자 정의 스타일로 테이블을 만드는 방법을 알게 됩니다.

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

## 3단계: 새 표 시작 및 셀 삽입
 테이블 구축을 시작하려면 다음을 사용합니다.`StartTable()` Document Builder의 메소드를 사용하여 테이블에 셀을 삽입합니다.`InsertCell()` 방법.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## 4단계: 표 스타일 정의
 이제 다음을 사용하여 테이블 스타일을 설정할 수 있습니다.`StyleIdentifier` 재산. 이 예에서는 "MediumShading1Accent1" 스타일을 사용하고 있습니다.

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## 5단계: 표에 스타일 옵션 적용
 다음을 사용하여 스타일에 따라 어떤 특성을 형식화해야 하는지 지정할 수 있습니다.`StyleOptions`배열의 속성입니다. 이 예에서는 "FirstColumn", "RowBands" 및 "FirstRow" 옵션을 적용합니다.

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## 6단계: 테이블 크기 자동 조정
 내용에 따라 배열의 크기를 자동으로 조정하기 위해 다음을 사용합니다.`AutoFit()` 방법`AutoFitBehavior.AutoFitToContents` 행동.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## 7단계: 셀에 콘텐츠 추가
 이제 다음을 사용하여 셀에 내용을 추가할 수 있습니다.`Writeln()` 그리고`InsertCell()` 문서 작성기의 메소드. 이 예에서는 "Item" 및 "Quantity(

kg)" 및 해당 데이터.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## 8단계: 수정된 문서 저장
마지막으로 수정된 문서를 파일에 저장합니다. 출력 문서에 대한 적절한 이름과 위치를 선택할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

축하합니다! 이제 .NET용 Aspose.Words를 사용하여 사용자 정의 스타일 테이블을 만들었습니다.

### .NET용 Aspose.Words를 사용하여 스타일로 테이블 만들기의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// 테이블 형식을 설정하기 전에 먼저 최소한 하나의 행을 삽입해야 합니다.
	builder.InsertCell();
	// 고유 스타일 식별자를 기반으로 사용되는 테이블 스타일을 설정합니다.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// 스타일에 따라 형식을 지정해야 하는 기능을 적용합니다.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 스타일이 지정된 테이블을 작성하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 Word 문서의 표 스타일을 쉽게 사용자 지정할 수 있습니다. Aspose.Words는 문서의 표를 조작하고 서식을 지정하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 통해 Word 문서의 시각적 표현을 개선하고 특정 요구 사항을 충족할 수 있습니다.