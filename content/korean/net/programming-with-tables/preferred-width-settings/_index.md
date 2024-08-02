---
title: 기본 너비 설정
linktitle: 기본 너비 설정
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 Aspose.Words for .NET에서 절대, 상대 및 자동 너비 설정을 사용하여 테이블을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/preferred-width-settings/
---
## 소개

표는 Word 문서의 정보를 구성하고 표시하는 강력한 방법입니다. .NET용 Aspose.Words에서 테이블 작업을 할 때 문서 레이아웃에 완벽하게 맞도록 테이블 셀의 너비를 설정하는 몇 가지 옵션이 있습니다. 이 가이드는 절대, 상대 및 자동 크기 조정 옵션에 중점을 두고 Aspose.Words for .NET을 사용하여 기본 너비 설정으로 테이블을 만드는 과정을 안내합니다. 

## 전제 조건

튜토리얼을 시작하기 전에 다음 사항을 확인하세요.

1.  .NET용 Aspose.Words: 개발 환경에 .NET용 Aspose.Words가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/words/net/).

2. .NET 개발 환경: Visual Studio와 같은 .NET 개발 환경을 설정합니다.

3. C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 코드 조각과 예제를 더 잘 이해하는 데 도움이 됩니다.

4.  Aspose.Words 문서:[Aspose.Words 문서](https://reference.aspose.com/words/net/) 자세한 API 정보 및 추가 자료를 보려면

## 네임스페이스 가져오기

코딩을 시작하기 전에 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

이러한 네임스페이스는 Aspose.Words 및 Table 개체의 핵심 기능에 대한 액세스를 제공하여 문서 테이블을 조작할 수 있게 해줍니다.

다양한 기본 너비 설정을 사용하여 테이블을 만드는 과정을 명확하고 관리하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 문서 및 DocumentBuilder 초기화

표제: 새 문서 및 DocumentBuilder 만들기

 설명: 새 Word 문서를 만드는 것부터 시작하세요.`DocumentBuilder` 사례. 그만큼`DocumentBuilder` 클래스는 문서에 콘텐츠를 추가하는 간단한 방법을 제공합니다.

```csharp
// 문서를 저장할 경로를 정의합니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 새 문서를 만듭니다.
Document doc = new Document();

// 이 문서에 대한 DocumentBuilder를 만듭니다.
DocumentBuilder builder = new DocumentBuilder(doc);
```

 여기에서는 문서가 저장될 디렉터리를 지정하고`Document`그리고`DocumentBuilder` 사물.

## 2단계: 절대 너비의 첫 번째 표 셀 삽입

첫 번째 셀을 고정 너비 40포인트로 테이블에 삽입합니다. 이렇게 하면 이 셀이 테이블 크기에 관계없이 항상 40포인트 너비를 유지하게 됩니다.

```csharp

// 절대 크기의 셀을 삽입합니다.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell at 40 points width");
```

이 단계에서는 테이블 생성을 시작하고 절대 너비의 셀을 삽입합니다. 그만큼`PreferredWidth.FromPoints(40)` 메서드는 셀 너비를 40포인트로 설정하고`Shading.BackgroundPatternColor` 연한 노란색 배경색을 적용합니다.

## 3단계: 상대적 크기의 셀 삽입

테이블 전체 너비의 20%인 너비를 가진 다른 셀을 삽입합니다. 이러한 상대적 크기 조정을 통해 셀이 테이블 너비에 비례하여 조정됩니다.

```csharp
// 상대(백분율) 크기의 셀을 삽입합니다.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell at 20% width");
```

이 셀의 너비는 표 전체 너비의 20%이므로 다양한 화면 크기나 문서 레이아웃에 맞게 조정할 수 있습니다.

### 4단계: 자동 크기 셀 삽입

마지막으로, 테이블에 남아 있는 사용 가능한 공간에 따라 자동으로 크기가 조정되는 셀을 삽입합니다.

```csharp
// 자동 크기의 셀을 삽입합니다.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Cell automatically sized. The size of this cell is calculated from the table preferred width.");
builder.Writeln("In this case the cell will fill up the rest of the available space.");
```

 그만큼`PreferredWidth.Auto` 설정을 사용하면 다른 셀을 고려한 후 남은 공간을 기준으로 이 셀을 확장하거나 축소할 수 있습니다. 이렇게 하면 테이블 레이아웃이 균형있고 전문적으로 보입니다.

## 5단계: 문서 마무리 및 저장

모든 셀을 삽입한 후 테이블을 완성하고 문서를 지정된 경로에 저장합니다.

```csharp
// 문서를 저장합니다.
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

이 단계에서는 테이블을 마무리하고 지정된 디렉터리에 "WorkingWithTables.PreferredWidthSettings.docx"라는 파일 이름으로 문서를 저장합니다.

## 결론

사용 가능한 다양한 크기 조정 옵션을 이해하면 Aspose.Words for .NET에서 기본 너비 설정으로 테이블을 만드는 것은 간단합니다. 고정, 상대 또는 자동 셀 너비가 필요한지 여부에 관계없이 Aspose.Words는 다양한 테이블 레이아웃 시나리오를 효율적으로 처리할 수 있는 유연성을 제공합니다. 이 가이드에 설명된 단계를 수행하면 Word 문서에서 테이블이 잘 구조화되고 시각적으로 매력적인지 확인할 수 있습니다.

## FAQ

### 절대 셀 너비와 상대 셀 너비의 차이점은 무엇입니까?
절대 셀 너비는 고정되어 변경되지 않는 반면, 상대 너비는 테이블의 전체 너비에 따라 조정됩니다.

### 상대 너비에 음수 백분율을 사용할 수 있나요?
아니요, 음수 백분율은 셀 너비에 유효하지 않습니다. 양수 비율만 허용됩니다.

### 자동 크기 조정 기능은 어떻게 작동하나요?
자동 크기 조정은 다른 셀의 크기를 조정한 후 테이블의 남은 공간을 채우기 위해 셀 너비를 조정합니다.

### 너비 설정이 다른 셀에 다른 스타일을 적용할 수 있나요?
예, 너비 설정에 관계없이 셀에 다양한 스타일과 서식을 적용할 수 있습니다.

### 테이블의 전체 너비가 모든 셀 너비의 합보다 작으면 어떻게 되나요?
테이블은 사용 가능한 공간에 맞게 셀 너비를 자동으로 조정하므로 일부 셀이 줄어들 수 있습니다.