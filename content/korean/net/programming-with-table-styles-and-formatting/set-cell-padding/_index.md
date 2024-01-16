---
title: 셀 패딩 설정
linktitle: 셀 패딩 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 표 셀 여백을 설정하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 테이블 셀 여백을 설정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 Word 문서에 있는 테이블의 셀 내용의 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백(공간)을 조정하는 방법을 알게 됩니다.

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
builder. StartTable();
builder. InsertCell();
```

## 4단계: 셀 여백 설정
 이제 다음을 사용하여 셀 여백을 설정할 수 있습니다.`SetPaddings()` 의 방법`CellFormat` 물체. 여백은 포인트 단위로 정의되며 왼쪽, 위쪽, 오른쪽, 아래쪽 순서로 지정됩니다.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## 5단계: 셀에 콘텐츠 추가
 그런 다음 문서 작성기의`Writeln()` 방법.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## 6단계: 표 완성 및 문서 저장
 마지막으로, 다음을 사용하여 테이블 생성을 완료합니다.`EndRow()` 방법과`EndTable()`, 수정된 문서를 파일에 저장합니다.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### .NET용 Aspose.Words를 사용하여 셀 패딩 설정에 대한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// 셀 내용의 왼쪽/위/오른쪽/아래에 추가할 공간의 양(포인트)을 설정합니다.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테이블 셀의 여백을 설정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 셀 여백을 쉽게 조정하여 Word 문서의 표 내용 왼쪽, 위쪽, 오른쪽 및 아래쪽에 공백을 만들 수 있습니다. Aspose.Words는 문서의 표를 조작하고 서식을 지정하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 특정 요구 사항에 맞게 테이블 형식을 사용자 정의할 수 있습니다.