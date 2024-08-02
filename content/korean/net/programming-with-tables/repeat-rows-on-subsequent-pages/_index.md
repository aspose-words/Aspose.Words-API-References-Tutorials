---
title: 후속 페이지에서 행 반복
linktitle: 후속 페이지에서 행 반복
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 반복되는 표 머리글 행이 있는 Word 문서를 만드는 방법을 알아보세요. 전문적이고 세련된 문서를 보장하려면 이 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---
## 소개

프로그래밍 방식으로 Word 문서를 만드는 것은 어려운 작업이 될 수 있으며, 특히 여러 페이지에 걸쳐 서식을 유지해야 하는 경우 더욱 그렇습니다. Word에서 표를 만들어 보았지만 머리글 행이 다음 페이지에서 반복되지 않는다는 것을 깨달은 적이 있습니까? 두려워하지 마세요! Aspose.Words for .NET을 사용하면 각 페이지에서 표 헤더가 반복되도록 쉽게 확인하여 문서에 전문적이고 세련된 모양을 제공할 수 있습니다. 이 튜토리얼에서는 간단한 코드 예제와 자세한 설명을 사용하여 이를 달성하는 단계를 안내합니다. 뛰어들어보자!

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1.  .NET용 Aspose.Words: 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
2. .NET Framework가 컴퓨터에 설치되어 있습니다.
3. .NET 개발을 지원하는 Visual Studio 또는 기타 IDE.
4. C# 프로그래밍에 대한 기본 이해.

계속 진행하기 전에 .NET용 Aspose.Words를 설치하고 개발 환경을 설정했는지 확인하세요.

## 네임스페이스 가져오기

시작하려면 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. C# 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

이러한 네임스페이스에는 Word 문서와 테이블을 조작하는 데 필요한 클래스와 메서드가 포함됩니다.

## 1단계: 문서 초기화

 먼저 새 Word 문서를 만들고`DocumentBuilder` 우리 테이블을 만들려고요.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 이 코드는 새 문서와`DocumentBuilder` 문서 구조를 구축하는 데 도움이 되는 개체입니다.

## 2단계: 테이블 시작 및 머리글 행 정의

다음으로, 테이블을 시작하고 후속 페이지에서 반복할 헤더 행을 정의하겠습니다.

```csharp
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
```

 여기서는 새 테이블을 시작하고`HeadingFormat`재산`true` 행이 머리글임을 나타내고 셀의 정렬과 너비를 정의합니다.

## 3단계: 테이블에 데이터 행 추가

이제 테이블에 여러 데이터 행을 추가하겠습니다. 이 행은 후속 페이지에서 반복되지 않습니다.

```csharp
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
    builder.InsertCell();
    builder.RowFormat.HeadingFormat = false;
    builder.Write("Column 1 Text");
    
    builder.InsertCell();
    builder.Write("Column 2 Text");
    builder.EndRow();
}
```

 이 루프는 각 행에 2개의 열이 포함된 50개의 데이터 행을 테이블에 삽입합니다. 그만큼`HeadingFormat` 로 설정되어 있습니다`false` 이러한 행은 헤더 행이 아니기 때문입니다.

## 4단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

그러면 문서 디렉터리에 지정된 이름으로 문서가 저장됩니다.

## 결론

그리고 거기에 있습니다! 단 몇 줄의 코드만으로 Aspose.Words for .NET을 사용하여 후속 페이지에 머리글 행이 반복되는 표가 포함된 Word 문서를 만들 수 있습니다. 이는 문서의 가독성을 향상시킬 뿐만 아니라 일관되고 전문적인 외관을 보장합니다. 이제 프로젝트에서 이것을 시도해 보세요!

## FAQ

### 헤더 행을 추가로 사용자 정의할 수 있나요?
 예, 속성을 수정하여 머리글 행에 추가 서식을 적용할 수 있습니다.`ParagraphFormat`, `RowFormat` , 그리고`CellFormat`.

### 테이블에 더 많은 열을 추가할 수 있나요?
 전적으로! 더 많은 셀을 삽입하여 필요에 따라 많은 열을 추가 할 수 있습니다.`InsertCell` 방법.

### 다음 페이지에서 다른 행이 반복되도록 하려면 어떻게 해야 합니까?
 행을 반복하려면`RowFormat.HeadingFormat`재산`true` 해당 특정 행에 대해.

### 문서의 기존 테이블에 이 방법을 사용할 수 있나요?
 예, 다음을 통해 기존 테이블에 액세스하여 수정할 수 있습니다.`Document` 개체와 유사한 서식을 적용합니다.

### .NET용 Aspose.Words에서 사용할 수 있는 다른 테이블 서식 옵션은 무엇입니까?
 Aspose.Words for .NET은 셀 병합, 테두리 설정 및 테이블 정렬을 포함한 광범위한 테이블 서식 옵션을 제공합니다. 확인해 보세요[선적 서류 비치](https://reference.aspose.com/words/net/) 상세 사항은.