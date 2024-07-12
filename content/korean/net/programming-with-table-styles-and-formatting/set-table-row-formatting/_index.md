---
title: 테이블 행 서식 설정
linktitle: 테이블 행 서식 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 테이블 행 형식을 설정하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 테이블 행 형식을 설정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 Word 문서에서 표 행의 높이와 패딩을 조정하는 방법을 알게 됩니다.

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

## 3단계: 새 테이블 시작 및 셀 추가
테이블 생성을 시작하려면 다음을 사용합니다.`StartTable()` 문서 생성자의 메소드를 사용하여 테이블에 셀을 추가합니다.`InsertCell()` 방법.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## 4단계: 줄 서식 정의
 이제 다음 항목에 액세스하여 행 형식을 설정할 수 있습니다.`RowFormat` 의 대상`DocumentBuilder` 물체. 해당 속성을 사용하여 줄 높이와 여백(패딩)을 설정할 수 있습니다.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 5단계: 표 여백 설정
 다음으로, 해당 속성에 액세스하여 테이블 패딩을 설정할 수 있습니다.`Table` 물체. 이러한 여백은 테이블의 모든 행에 적용됩니다.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 6단계: 행에 콘텐츠 추가
 마지막으로 문서 작성기의`Writeln()` 방법.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 7단계: 표 완성 및 문서 저장
~ 안에

 마지막으로 다음을 사용하여 테이블 생성을 마칩니다.`EndRow()`그리고`EndTable()` 방법을 사용하면 수정된 문서를 파일에 저장합니다.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### .NET용 Aspose.Words를 사용하여 테이블 행 서식 설정에 대한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// 이러한 서식 속성은 테이블에 설정되며 테이블의 모든 행에 적용됩니다.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 테이블 행 서식을 설정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 Word 문서에서 표 행 높이와 여백을 쉽게 조정할 수 있습니다. Aspose.Words는 문서의 표를 조작하고 서식을 지정하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 특정 요구 사항에 맞게 테이블의 시각적 레이아웃을 사용자 지정할 수 있습니다.