---
title: 행 서식 적용
linktitle: 행 서식 적용
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 테이블에 행 서식을 적용하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 테이블에 행 서식을 적용하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼을 마치면 .NET용 Aspose.Words를 사용하여 Word 문서에서 표 행의 형식을 지정하는 방법을 명확하게 이해하게 될 것입니다.

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

## 3단계: 새 보드 시작
 행 서식을 적용하려면 먼저 다음을 사용하여 새 테이블을 시작해야 합니다.`StartTable()` 문서 생성자의 메소드.

```csharp
Table table = builder. StartTable();
```

## 4단계: 셀을 삽입하고 행 형식으로 이동
이제 테이블에 셀을 삽입하고 문서 작성기의`InsertCell()` 그리고`RowFormat` 행동 양식.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## 5단계: 행 높이 설정
 행 높이를 설정하려면 다음을 사용합니다.`Height` 그리고`HeightRule` 행 형식의 속성입니다. 이 예에서는 행 높이를 100포인트로 설정하고`Exactly` 규칙.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 6단계: 테이블 형식 정의
 일부 서식 속성은 테이블 자체에 설정할 수 있으며 모든 테이블 행에 적용됩니다. 이 예에서는 다음을 사용하여 테이블 여백 속성을 설정합니다.`LeftPadding`, `RightPadding`, `TopPadding` 그리고`BottomPadding` 속성.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 7단계: 행에 콘텐츠 추가
이제 우리는 할 수 있습니다

 문서 생성자의 메서드를 사용하여 해당 줄에 내용을 추가하겠습니다. 이 예에서는`Writeln()` 줄에 텍스트를 추가하는 방법입니다.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 8단계: 선과 테이블 완성하기
 행에 내용을 추가한 후에는 다음을 사용하여 행을 끝낼 수 있습니다.`EndRow()` 메서드를 사용하여 테이블을 종료합니다.`EndTable()` 방법.

```csharp
builder. EndRow();
builder. EndTable();
```

## 9단계: 수정된 문서 저장
마지막으로 수정된 문서를 파일에 저장합니다. 출력 문서에 대한 적절한 이름과 위치를 선택할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 테이블에 행 서식을 적용했습니다.

### .NET용 Aspose.Words를 사용하여 행 서식 적용을 위한 샘플 소스 코드 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테이블에 행 서식을 적용하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 이 기능을 C# 프로젝트에 쉽게 통합할 수 있습니다. 테이블 행 서식을 조작하는 것은 문서 처리의 필수적인 측면이며 Aspose.Words는 이를 달성하기 위해 강력하고 유연한 API를 제공합니다. 이러한 지식을 통해 Word 문서의 시각적 표현을 개선하고 특정 요구 사항을 충족할 수 있습니다.