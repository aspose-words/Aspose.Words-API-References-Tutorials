---
title: 테두리가 다른 테이블과 셀 서식 지정
linktitle: 테두리가 다른 테이블과 셀 서식 지정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 테두리가 다른 테이블과 셀의 형식을 지정하는 단계별 안내입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 테두리가 다른 테이블과 셀의 서식을 지정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 Word 문서의 특정 테이블과 셀에 사용자 정의 테두리를 적용하는 방법을 알게 됩니다.

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
테이블 생성을 시작하려면 다음을 사용합니다.`StartTable()` Document Builder의 메소드를 사용하여 테이블에 셀을 추가합니다.`InsertCell()` 메서드를 사용하여 셀의 내용을 씁니다.`Writeln()` 방법.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// 전체 테이블에 테두리를 설정합니다.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// 이 셀에 패딩을 설정합니다.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// 두 번째 셀에 대해 다른 셀 패딩을 지정합니다.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// 이전 작업의 셀 서식을 지웁니다.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// 이 행의 첫 번째 셀에 대해 더 두꺼운 테두리를 만듭니다. 다를 것이다
// 테이블에 정의된 테두리를 기준으로 합니다.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## 4단계: 문서 저장

  수정된
마지막으로 수정된 문서를 파일로 저장합니다. 출력 문서에 대한 적절한 이름과 위치를 선택할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 테두리가 다른 테이블과 셀의 서식을 지정했습니다.

### .NET용 Aspose.Words를 사용하여 테두리가 다른 테이블 및 셀 서식 지정을 위한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//표 전체의 테두리를 설정합니다.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// 이 셀에 대한 셀 음영을 설정합니다.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// 두 번째 셀에 대해 다른 셀 음영을 지정합니다.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// 이전 작업에서 셀 서식을 지웁니다.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// 이 행의 첫 번째 셀에 대해 더 큰 테두리를 만듭니다. 이건 다를거야
	// 테이블에 설정된 테두리와 비교됩니다.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테두리가 다른 테이블과 셀의 서식을 지정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 Word 문서에서 표와 셀 테두리를 쉽게 사용자 지정할 수 있습니다. Aspose.Words는 문서의 표를 조작하고 서식을 지정하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 통해 Word 문서의 시각적 표현을 개선하고 특정 요구 사항을 충족할 수 있습니다.