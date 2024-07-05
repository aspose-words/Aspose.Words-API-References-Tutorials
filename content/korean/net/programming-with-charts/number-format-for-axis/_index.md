---
title: 차트의 축에 대한 숫자 형식
linktitle: 차트의 축에 대한 숫자 형식
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 차트 축의 숫자 형식을 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/number-format-for-axis/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트 축의 숫자 형식을 설정하는 방법을 설명합니다. 제공된 소스 코드는 차트를 만들고, 계열 데이터를 추가하고, 축 레이블 형식을 지정하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다. NuGet 패키지 관리자를 사용하여 다운로드하여 설치할 수 있습니다.
- 출력 문서가 저장될 문서 디렉터리 경로입니다.

## 2단계: 새 문서 만들기 및 차트 삽입

 새로 만들기`Document` 객체와`DocumentBuilder` 문서를 작성합니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 다음으로`InsertChart` 의 방법`DocumentBuilder` 문서에 세로 막대형 차트를 삽입하려면

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트에 계열 데이터 추가

차트에 계열 데이터를 추가합니다. 이 예에서는 해당 값과 함께 5개의 항목을 추가합니다.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## 4단계: 축 레이블 서식 지정

 Y축 레이블의 숫자 형식을 설정하려면`AxisY` 차트의 속성을 설정하고`NumberFormat.FormatCode` 속성을 원하는 형식으로 변경합니다. 이 예에서는 숫자를 천 단위 구분 기호로 표시하기 위해 형식을 "#,##0"으로 설정했습니다.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## 5단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 축의 숫자 형식 설정 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하는 축의 숫자 형식에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트 축의 숫자 형식을 설정하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 새 문서를 만들고, 세로 막대형 차트를 삽입하고, 계열 데이터를 추가하고, 축 레이블의 서식을 지정하여 숫자를 특정 형식으로 표시할 수 있습니다.

Aspose.Words for .NET은 Word 문서의 차트 모양을 사용자 정의하는 강력한 기능을 제공합니다. 축 레이블의 숫자 형식을 설정하면 소수 자릿수, 천 단위 구분 기호, 통화 기호 등과 같은 옵션을 포함하여 숫자가 표시되는 방식을 제어할 수 있습니다. 이를 통해 숫자 데이터를 명확하고 의미 있는 방식으로 표현할 수 있습니다.

.NET용 Aspose.Words를 사용하면 축 레이블을 포함하여 차트의 다양한 측면에 대한 형식을 유연하게 지정할 수 있습니다. 축의 숫자 형식을 설정하면 일관성을 보장하고 차트의 가독성을 향상시켜 사용자가 표시된 값을 더 쉽게 해석할 수 있습니다.

### 자주 묻는 질문

#### Q1. 차트 축의 숫자 형식은 무엇입니까?
차트 축의 숫자 형식은 축에 표시되는 숫자 값에 적용되는 형식을 나타냅니다. 소수 자릿수, 천 단위 구분 기호, 통화 기호, 백분율 기호 등과 같은 옵션을 포함하여 숫자가 표시되는 방식을 제어할 수 있습니다. 숫자 형식을 설정하면 특정 요구 사항에 맞게 차트의 숫자 데이터 모양을 사용자 정의할 수 있습니다.

#### Q2. 축 레이블의 숫자 형식을 어떻게 설정합니까?
 .NET용 Aspose.Words를 사용하여 차트의 축 레이블에 대한 숫자 형식을 설정하려면`AxisY` 차트의 속성을 설정하고`NumberFormat.FormatCode`속성을 원하는 형식 코드로 설정합니다. 형식 코드는 표준 숫자 형식 지정 패턴의 구문을 따르며 숫자 표시 방법을 결정합니다. 예를 들어 "#,##0.00"을 사용하면 소수점 두 자리와 천 단위 구분 기호를 사용하여 숫자를 표시할 수 있습니다.

#### Q3. X축과 Y축 레이블에 서로 다른 숫자 형식을 설정할 수 있나요?
예, Aspose.Words for .NET을 사용하여 X축 및 Y축 레이블에 대해 서로 다른 숫자 형식을 설정할 수 있습니다. 해당 축에 액세스합니다(`AxisX` X축의 경우 또는`AxisY` Y축의 경우) 차트의`NumberFormat.FormatCode` 각 축에 대해 개별적으로 속성을 지정합니다. 이를 통해 특정 요구 사항에 따라 각 축의 레이블에 다양한 숫자 형식을 적용할 수 있습니다.

#### Q4. 사용할 수 있는 일반적인 숫자 형식 코드는 무엇입니까?
Aspose.Words for .NET은 차트의 축 레이블 형식을 지정하는 데 사용할 수 있는 광범위한 숫자 형식 코드를 지원합니다. 몇 가지 일반적인 형식 코드는 다음과 같습니다.

- `0` 또는`#` - 소수점 이하 자릿수 없이 숫자를 표시합니다.
- `0.00` 또는`#.00` - 소수점 이하 두 자리까지 숫자를 표시합니다.
- `#,##0` 천 단위 구분 기호로 숫자를 표시합니다.
- `"€"0.00` - 유로화 기호와 소수점 이하 두 자리를 사용하여 숫자를 표시합니다.
- `"%"0` - 숫자를 백분율로 표시합니다.

 번호에 대한 자세한 정보를 확인할 수 있습니다.[형식 코드](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) .NET용 Aspose.Words의 API 참조에서.

#### Q5. 축 레이블의 다른 속성을 사용자 정의할 수 있나요?
예, .NET용 Aspose.Words는 축 레이블의 모양과 동작을 사용자 정의할 수 있는 광범위한 속성을 제공합니다. 숫자 형식 외에도 글꼴, 크기, 색상, 방향, 정렬 등과 같은 속성을 수정할 수 있습니다. 이를 통해 원하는 스타일 및 프리젠테이션 요구 사항에 맞게 축 레이블을 완전히 사용자 정의할 수 있습니다.