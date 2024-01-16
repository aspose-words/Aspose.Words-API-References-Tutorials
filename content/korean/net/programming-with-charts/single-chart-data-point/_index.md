---
title: 차트의 단일 차트 데이터 포인트 사용자 정의
linktitle: 차트의 단일 차트 데이터 포인트 사용자 정의
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 차트의 단일 데이터 포인트를 사용자 정의하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/single-chart-data-point/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 단일 데이터 포인트를 사용자 정의하는 방법을 설명합니다. 제공된 소스 코드는 차트를 만들고, 특정 데이터 포인트에 액세스하고, 해당 속성을 수정하는 방법을 보여줍니다.

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

 다음으로`InsertChart` 의 방법`DocumentBuilder` 문서에 꺾은선형 차트를 삽입하려면

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 데이터 포인트에 액세스하고 맞춤설정하세요.

 개별 데이터 포인트를 수정하려면`ChartDataPointCollection` 시리즈의 인덱스를 사용하여 원하는 데이터 포인트를 선택합니다.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## 4단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 차트의 단일 데이터 포인트를 사용자 정의하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하는 단일 차트 데이터 포인트의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 단일 데이터 포인트를 사용자 정의하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하여 새 문서를 만들고, 꺾은선형 차트를 삽입하고, 차트 시리즈 내의 특정 데이터 포인트에 액세스하고, 해당 속성을 수정하여 원하는 사용자 정의를 얻을 수 있습니다.

Aspose.Words for .NET은 Word 문서의 차트를 조작할 수 있는 강력한 기능을 제공합니다. 차트 시리즈 내의 개별 데이터 포인트에 액세스하면 특정 수정 사항을 적용하여 모양과 동작을 맞춤 설정할 수 있습니다. 이를 통해 특정 데이터 포인트를 강조 표시하고, 마커 기호를 변경하고, 마커 크기를 조정하는 등 차트의 시각적 표현을 향상시킬 수 있습니다.

개별 데이터 포인트를 사용자 정의하면 차트에서 중요한 데이터를 강조하거나 특정 추세를 강조할 수 있는 유연성이 제공됩니다. Aspose.Words for .NET을 사용하면 다양한 차트 유형의 데이터 포인트에 쉽게 액세스하고 수정할 수 있으므로 Word 문서에서 시각적으로 매력적이고 유익한 차트를 만들 수 있습니다.

### 자주 묻는 질문

#### Q1. 차트의 여러 데이터 포인트를 맞춤설정할 수 있나요?
 예, Aspose.Words for .NET을 사용하여 차트의 여러 데이터 포인트를 사용자 정의할 수 있습니다. 액세스하여`ChartDataPointCollection`시리즈의 경우 해당 색인을 기반으로 여러 데이터 포인트를 선택하고 수정할 수 있습니다. 루프 또는 개별 할당을 사용하여 각 데이터 포인트에 대해 원하는 속성을 수정합니다. 이렇게 하면 동일한 차트 내의 여러 데이터 포인트에 다양한 사용자 정의를 적용할 수 있습니다.

#### Q2. 데이터 포인트의 마커 기호를 어떻게 변경할 수 있나요?
 .NET용 Aspose.Words를 사용하여 차트의 데이터 포인트에 대한 마커 기호를 변경하려면`Marker` 의 재산`ChartDataPoint` 객체를 설정하고`Symbol` 속성을 원하는 마커 기호에 추가합니다. 마커 기호는 차트의 각 데이터 포인트를 나타내는 데 사용되는 모양이나 아이콘을 나타냅니다. 원, 사각형, 다이아몬드, 삼각형, 별 등과 같은 다양한 내장 마커 기호 중에서 선택할 수 있습니다.

#### Q3. 데이터 포인트 마커의 크기를 조정할 수 있나요?
 예, Aspose.Words for .NET을 사용하여 차트의 데이터 포인트 마커 크기를 조정할 수 있습니다. 액세스`Marker` 의 재산`ChartDataPoint` 객체를 설정하고`Size`속성을 원하는 마커 크기로 설정합니다. 마커의 크기는 일반적으로 포인트 단위로 지정되며, 값이 클수록 마커 크기가 더 커집니다. 마커 크기를 조정하면 특정 데이터 포인트를 강조하거나 중요성에 따라 차별화할 수 있습니다.

#### Q4. 데이터 포인트에 대해 수정할 수 있는 다른 속성은 무엇입니까?
Aspose.Words for .NET은 차트의 데이터 포인트에 대해 수정할 수 있는 다양한 속성을 제공합니다. 일반적으로 수정되는 속성에는 마커 기호, 마커 크기, 마커 색상, 데이터 레이블 가시성, 폭발, 음수인 경우 반전 등이 포함됩니다. 이러한 속성을 사용하면 개별 데이터 포인트의 모양, 동작 및 상호 작용을 사용자 정의하여 특정 요구 사항에 맞는 차트를 만들 수 있습니다.

#### Q5. 다른 차트 유형의 데이터 포인트를 맞춤설정할 수 있나요?
예, Aspose.Words for .NET을 사용하여 다양한 차트 유형의 데이터 포인트를 사용자 정의할 수 있습니다. 이 튜토리얼에서는 꺾은선형 차트의 데이터 포인트를 사용자 정의하는 방법을 보여 주지만 세로 막대형 차트, 막대형 차트, 원형 차트 등과 같은 다른 차트 유형에도 유사한 기술을 적용할 수 있습니다. 이 프로세스에는 차트 내의 계열 및 데이터 요소에 액세스하고 그에 따라 해당 속성을 수정하는 작업이 포함됩니다.