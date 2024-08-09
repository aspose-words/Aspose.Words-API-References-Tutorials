---
title: 서식이 지정된 테이블
linktitle: 서식이 지정된 테이블
second_title: Aspose.Words 문서 처리 API
description: 이 상세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 테이블을 만들고 서식을 지정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/formatted-table/
---
## 소개

프로그래밍 방식으로 Word 문서에서 테이블을 만들고 서식을 지정하는 것은 어려운 작업처럼 보일 수 있지만 .NET용 Aspose.Words를 사용하면 간단하고 관리하기 쉬워집니다. 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 서식이 지정된 테이블을 만드는 방법을 안내합니다. 환경 설정부터 문서 저장까지 아름다운 형식의 표로 모든 것을 다룹니다.

## 전제 조건

코드를 살펴보기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

1. .NET 라이브러리용 Aspose.Words: 다음에서 다운로드하세요.[여기](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio와 같은 IDE.
3. .NET Framework: 컴퓨터에 .NET Framework가 설치되어 있는지 확인하세요.

## 네임스페이스 가져오기

실제 코드를 작성하기 전에 필요한 네임스페이스를 가져와야 합니다.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## 1단계: 문서 디렉토리 설정

먼저 문서가 저장될 경로를 정의해야 합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서를 저장하려는 실제 경로를 사용하십시오.

## 2단계: 문서 및 DocumentBuilder 초기화

이제 새 문서와 DocumentBuilder 개체를 초기화합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 그만큼`DocumentBuilder` 문서 작성 과정을 단순화하는 도우미 클래스입니다.

## 3단계: 테이블 시작

 다음으로, 다음을 사용하여 테이블 생성을 시작합니다.`StartTable` 방법.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

테이블을 시작하려면 셀을 삽입해야 합니다.

## 4단계: 표 전체 서식 적용

전체 표에 영향을 미치는 서식을 적용할 수 있습니다. 예를 들어 왼쪽 들여쓰기를 설정하면 다음과 같습니다.

```csharp
table.LeftIndent = 20.0;
```

## 5단계: 머리글 행 서식 지정

머리글 행의 높이, 정렬 및 기타 속성을 설정합니다.

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

이 단계에서는 배경색, 글꼴 크기, 정렬을 설정하여 머리글 행을 눈에 띄게 만듭니다.

## 6단계: 추가 헤더 셀 삽입

머리글 행에 더 많은 셀을 삽입합니다.

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## 7단계: 본문 행 형식 지정

헤더를 설정한 후 테이블 본문의 형식을 지정합니다.

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## 8단계: 본문 행 삽입

내용이 포함된 본문 행을 삽입합니다.

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

추가 행에 대해 반복합니다.

```csharp
builder.InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Row 2, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 2, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 2, Cell 3 Content.");
builder.EndRow();
builder.EndTable();
```

## 9단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

그러면 서식이 지정된 표가 포함된 Word 문서가 생성되고 저장됩니다.

## 결론

그리고 거기에 있습니다! 다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 Word 문서에 올바른 형식의 테이블을 만들 수 있습니다. 이 강력한 라이브러리를 사용하면 Word 문서를 프로그래밍 방식으로 쉽게 조작하여 시간과 노력을 절약할 수 있습니다.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 프로그래밍 방식으로 Word 문서를 생성, 편집 및 변환하기 위한 강력한 라이브러리입니다.

### 행마다 다른 색상을 사용할 수 있나요?
예, 색상을 비롯한 다양한 서식을 행이나 셀마다 적용할 수 있습니다.

### .NET용 Aspose.Words는 무료인가요?
 Aspose.Words for .NET은 유료 라이브러리이지만[무료 평가판](https://releases.aspose.com/).

### .NET용 Aspose.Words에 대한 지원을 받으려면 어떻게 해야 합니까?
 에서 지원을 받으실 수 있습니다.[Aspose 커뮤니티 포럼](https://forum.aspose.com/c/words/8).

### Aspose.Words for .NET을 사용하여 다른 유형의 문서를 만들 수 있나요?
예, Aspose.Words for .NET은 PDF, HTML, TXT를 포함한 다양한 문서 형식을 지원합니다.