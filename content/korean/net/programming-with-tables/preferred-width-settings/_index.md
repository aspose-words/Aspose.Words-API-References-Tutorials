---
title: 기본 너비 설정
linktitle: 기본 너비 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 기본 테이블 셀 너비를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/preferred-width-settings/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 표 셀의 기본 너비 설정을 지정하는 방법을 알아봅니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 Word 문서의 표 셀에 대해 다양한 기본 너비를 지정할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 생성 및 문서 생성기 초기화
문서 및 문서 생성기로 단어 처리를 시작하려면 다음 단계를 따르십시오.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서작성
Document doc = new Document();

// 문서 생성기 초기화
DocumentBuilder builder = new DocumentBuilder(doc);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 원하는 너비로 테이블 만들기
다음으로, 선호하는 너비가 서로 다른 세 개의 셀이 포함된 테이블을 작성하겠습니다. 다음 코드를 사용하세요.

```csharp
// 테이블의 시작
builder. StartTable();

// 절대 크기의 셀 삽입
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// 상대적 크기(백분율)의 셀 삽입
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// 자동 크기 셀 삽입
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// 테이블 끝
builder. EndTable();
```

여기서는 문서 작성기를 사용하여 세 개의 셀이 있는 테이블을 만듭니다. 첫 번째 셀의 기본 너비는 40포인트이고, 두 번째 셀의 기본 너비는 테이블 너비의 20%이며, 세 번째 셀의 기본 너비는 자동으로 조정됩니다.

  사용 가능한 공간에 따라.

## 4단계: 수정된 문서 저장
마지막으로, 테이블 셀에 대해 정의된 기본 너비 설정을 사용하여 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 기본 너비 설정에 대한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// 선호하는 너비가 서로 다른 세 개의 셀로 구성된 테이블 행을 삽입합니다.
	builder.StartTable();
	// 절대 크기의 셀을 삽입합니다.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// 상대(백분율) 크기의 셀을 삽입합니다.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// 자동 크기의 셀을 삽입합니다.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 표 셀의 기본 너비 설정을 지정하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서의 특정 요구 사항에 맞게 표 셀 너비를 사용자 지정할 수 있습니다.