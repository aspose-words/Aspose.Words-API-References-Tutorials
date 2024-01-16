---
title: 페이지 너비에 자동 맞춤
linktitle: 페이지 너비에 자동 맞춤
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 페이지 너비에 표를 자동으로 맞추는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/auto-fit-to-page-width/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서의 페이지 너비에 테이블을 자동으로 맞추는 방법을 배웁니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서의 테이블을 조작할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 생성 및 구성
테이블을 사용하여 단어 처리를 시작하려면 문서를 만들고 문서 생성기를 구성해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 및 문서 생성기 만들기
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 테이블 삽입 및 구성
다음으로, 페이지 너비의 절반을 차지하는 너비의 표를 문서에 삽입하겠습니다. 다음 코드를 사용하세요.

```csharp
// 테이블 삽입 및 너비 구성
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

여기서는 문서 작성기를 사용하여 테이블 만들기를 시작하고, 셀을 삽입하고, 테이블의 기본 너비를 페이지 너비의 50%로 설정합니다. 그런 다음 각 셀에 텍스트를 추가합니다.

## 4단계: 수정된 문서 저장
마지막으로 페이지 너비에 맞게 테이블을 조정하여 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
// 수정된 문서를 저장하세요
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.
  
### .NET용 Aspose.Words를 사용하여 페이지 너비에 자동 맞춤을 위한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// 페이지 너비의 절반을 차지하는 너비의 표를 삽입합니다.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서의 페이지 너비에 표를 자동으로 맞추는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서의 테이블을 프로그래밍 방식으로 조작할 수 있습니다. 이 기능을 사용하면 페이지에 따라 표의 너비를 동적으로 조정할 수 있으므로 전문적이고 시각적으로 매력적인 문서를 제공할 수 있습니다.