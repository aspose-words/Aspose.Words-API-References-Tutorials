---
title: 스타일에서 셀 및 행의 서식 확장
linktitle: 스타일에서 셀 및 행의 서식 확장
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 테이블 스타일에서 셀과 행으로 서식을 확장하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 스타일에서 셀과 행으로 서식을 확장하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 Word 문서의 특정 셀과 행에 표 스타일 서식을 적용하는 방법을 알게 됩니다.


## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 여기에 Word 문서가 있는 곳입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 기존 문서 로드
 다음으로 기존 Word 문서를 인스턴스로 로드해야 합니다.`Document` 수업.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3단계: 첫 번째 테이블의 첫 번째 셀로 이동
 시작하려면 문서에 있는 첫 번째 테이블의 첫 번째 셀로 이동해야 합니다. 우리는`GetChild()` 그리고`FirstRow.FirstCell` 첫 번째 셀에 대한 참조를 가져오는 방법입니다.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## 4단계: 초기 셀 서식 표시
테이블 스타일을 확장하기 전에 셀의 현재 배경색을 표시합니다. 현재 서식이 테이블 스타일에 저장되어 있으므로 이 필드는 비어 있어야 합니다.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## 5단계: 표 스타일을 직접 서식으로 확장
 이제 문서의 스타일을 사용하여 표 스타일을 직접 서식으로 확장합니다.`ExpandTableStylesToDirectFormatting()` 방법.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## 6단계: 스타일 확장 후 셀 서식 표시
이제 테이블 스타일을 확장한 후 셀의 배경색을 표시합니다. 파란색 배경색은 테이블 스타일에서 적용해야 합니다.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### .NET용 Aspose.Words를 사용하여 스타일에서 셀 및 행 서식 확장에 대한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// 문서의 첫 번째 테이블의 첫 번째 셀을 가져옵니다.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// 먼저 셀 음영의 색상을 인쇄합니다.
	// 현재 음영처리가 테이블 스타일에 저장되어 있으므로 이는 비어 있어야 합니다.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// 이제 테이블 스타일을 확장한 후 셀 음영을 인쇄합니다.
	// 파란색 배경 패턴 색상은 테이블 스타일에서 적용했어야 합니다.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테이블 스타일에서 셀과 행으로 서식을 확장하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 Word 문서의 특정 셀과 행에 표 스타일 서식을 쉽게 적용할 수 있습니다. Aspose.Words는 문서의 표를 조작하고 서식을 지정하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 Word 문서의 레이아웃과 프레젠테이션을 추가로 사용자 정의할 수 있습니다.