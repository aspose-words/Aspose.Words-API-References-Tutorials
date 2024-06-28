---
title: 차트에서 단일 차트 시리즈 사용자 정의
linktitle: 차트에서 단일 차트 시리즈 사용자 정의
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 차트에서 단일 차트 시리즈를 사용자 정의하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/single-chart-series/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 단일 차트 시리즈를 사용자 정의하는 방법을 설명합니다. 제공된 소스 코드는 차트를 만들고, 특정 계열에 액세스하고, 해당 속성을 수정하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다. NuGet 패키지 관리자를 사용하여 다운로드하여 설치할 수 있습니다.
- 출력 문서가 저장될 문서 디렉터리 경로입니다.

## 2단계: 새 문서를 만들고 차트를 삽입합니다.

 새로 만들기`Document` 객체와`DocumentBuilder` 문서를 작성합니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 다음으로`InsertChart` 의 방법`DocumentBuilder` 문서에 꺾은선형 차트를 삽입하려면

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트 시리즈 액세스 및 사용자 지정

 단일 차트 시리즈를 수정하려면`ChartSeries` 차트의 개체입니다.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## 4단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 단일 차트 시리즈를 사용자 정의하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하는 단일 차트 시리즈의 소스 코드 예 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Catmull-Rom 스플라인을 사용하여 차트의 점을 연결하는 선을 부드럽게 처리할지 여부를 지정할 수도 있습니다.
	series0.Smooth = true;
	series1.Smooth = true;
	// 값이 음수인 경우 기본적으로 상위 요소의 색상을 반전할지 여부를 지정합니다.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트에서 단일 차트 시리즈를 사용자 정의하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하여 새 문서를 만들고, 꺾은선형 차트를 삽입하고, 특정 차트 시리즈에 액세스하고, 해당 속성을 수정하여 원하는 사용자 정의를 얻을 수 있습니다.

Aspose.Words for .NET은 Word 문서의 차트를 조작할 수 있는 강력한 기능을 제공합니다. 개별 차트 시리즈에 액세스하면 특정 수정 사항을 적용하여 모양과 동작을 사용자 정의할 수 있습니다. 이를 통해 시리즈 이름을 변경하고, 차트 선을 부드럽게 하고, 데이터 포인트에 대한 표식을 사용자 정의하고, 음수 값에 대해 색상을 반전시키는 등 차트의 시각적 표현을 향상시킬 수 있습니다.

단일 차트 시리즈를 사용자 정의하면 차트 내에서 특정 데이터를 강조하거나 특정 추세를 강조할 수 있는 유연성이 제공됩니다. Aspose.Words for .NET을 사용하면 차트 시리즈 속성에 쉽게 액세스하고 수정할 수 있으므로 Word 문서에서 시각적으로 매력적이고 유익한 차트를 만들 수 있습니다.

### 자주 묻는 질문

#### Q1. 하나의 차트에서 여러 차트 시리즈를 맞춤설정할 수 있나요?
 예, Aspose.Words for .NET을 사용하여 차트의 여러 차트 시리즈를 사용자 정의할 수 있습니다. 액세스하여`ChartSeries`차트 내의 개체를 사용하면 해당 지수나 특정 기준에 따라 여러 계열을 선택하고 수정할 수 있습니다. 루프 또는 개별 할당을 사용하여 각 차트 시리즈에 대해 원하는 속성을 수정합니다. 이렇게 하면 동일한 차트 내의 여러 시리즈에 다양한 사용자 정의를 적용할 수 있습니다.

#### Q2. 차트 시리즈의 이름을 어떻게 변경할 수 있나요?
 Aspose.Words for .NET을 사용하여 차트의 차트 시리즈 이름을 변경하려면`Name` 의 재산`ChartSeries` 개체를 선택하고 원하는 이름으로 설정합니다. 계열 이름은 일반적으로 차트 범례 또는 데이터 레이블에 표시되어 계열에 대한 설명 레이블을 제공합니다. 시리즈 이름을 수정하면 각 시리즈가 나타내는 데이터를 반영하는 의미 있는 이름을 제공할 수 있습니다.

#### Q3. 차트 계열 평활화란 무엇입니까?
차트 계열 평활화는 차트의 점을 연결하는 부드러운 선을 만들 수 있는 시각적 향상 기술입니다. Catmull-Rom 스플라인과 같은 평활화 알고리즘을 적용하여 데이터 포인트 사이를 보간하고 시각적으로 보기 좋은 곡선을 만듭니다. .NET용 Aspose.Words를 사용하여 차트에서 계열 평활화를 활성화하려면`Smooth` 의 재산`ChartSeries` 개체를 설정하고`true`. 평활화는 불규칙한 변동이 있는 데이터의 추세나 패턴을 표시하는 데 유용할 수 있습니다.

#### Q4. 차트 시리즈의 데이터 포인트에 대한 마커를 어떻게 사용자 정의할 수 있나요?
 .NET용 Aspose.Words를 사용하여 차트 시리즈의 데이터 포인트에 대한 마커를 사용자 정의하려면`Marker` 의 재산`ChartSeries` 객체를 만들고 다음과 같은 속성을 수정합니다.`Symbol` 그리고`Size`. 마커는 개별 데이터 포인트를 나타내기 위해 차트에 배치되는 시각적 표시기입니다. 다양한 내장 마커 기호 중에서 선택하고 크기를 조정하여 시리즈 내의 특정 데이터 포인트를 강조 표시하거나 차별화할 수 있습니다.

#### Q5. 차트 시리즈에서 음수 값의 색상을 반전할 수 있나요?
 예, Aspose.Words for .NET을 사용하여 차트 시리즈의 음수 값에 대한 색상을 반전시킬 수 있습니다. 설정하여`InvertIfNegative` 의 재산`ChartSeries` 반대하다`true`, 음수 값이 있는 데이터 포인트의 색상이 반전되어 양수 값과 시각적으로 구별됩니다. 이 기능은 차트 계열의 양수 값과 음수 값을 비교할 때 유용하며 둘 사이의 명확한 차별화를 제공합니다.