---
title: 차트에서 XY 축 속성 정의
linktitle: 차트에서 XY 축 속성 정의
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 차트에서 XY 축 속성을 정의하는 방법을 알아보세요. X 및 Y축에 대한 사용자 정의 옵션이 설명됩니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/define-xyaxis-properties/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 X 및 Y 축 속성을 정의하는 방법을 설명합니다. 제공된 소스 코드는 차트를 만들고, 계열 데이터를 추가하고, 축 속성을 사용자 지정하는 방법을 보여줍니다.

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

 다음으로,`InsertChart` 의 방법`DocumentBuilder`. 이 예에서는 영역 차트를 삽입하겠습니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트에 계열 데이터 추가

차트에 계열 데이터를 추가합니다. 이 예에서는 해당 날짜 및 값이 포함된 5개의 데이터 요소를 추가합니다.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## 4단계: X 및 Y축 속성 사용자 정의

 X축과 Y축의 속성을 사용자 정의하려면`ChartAxis` 차트와 관련된 개체입니다.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 속성을 수정합니다.`xAxis` 그리고`yAxis` 및 Y 축에 대해 원하는 옵션을 설정하는 개체입니다. 이 예에서는 사용자 정의할 수 있는 몇 가지 공통 속성을 보여줍니다.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## 5단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 차트에서 XY 축 속성을 정의하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 XYAxis 속성 정의에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// 차트 삽입
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// X축을 날짜 대신 카테고리로 변경하면 모든 포인트가 X축에 동일한 간격으로 배치됩니다.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Y축의 표시 단위(백)로 측정됩니다.
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 X 및 Y 축 속성을 정의하는 방법을 배웠습니다. 단계별 가이드에 따라 차트를 만들고, 계열 데이터를 추가하고, 특정 요구 사항에 맞게 축 속성을 사용자 지정할 수 있습니다. Aspose.Words for .NET은 Word 문서의 차트를 사용하여 단어 처리를 위한 포괄적인 API를 제공하므로 축을 포함하여 차트의 다양한 측면을 조작할 수 있습니다.

액세스하여`ChartAxis` 차트와 연결된 개체의 경우 범주 유형, 축 교차, 눈금 표시, 레이블 위치, 배율 등과 같은 속성을 수정할 수 있습니다. 이러한 유연성을 통해 차트 축의 모양과 동작을 맞춤화하여 데이터를 효과적으로 표시할 수 있습니다.

.NET용 Aspose.Words를 사용하면 차트 생성 및 사용자 정의 기능을 .NET 애플리케이션에 원활하게 통합하고 풍부한 시각화 기능을 갖춘 전문가 수준의 문서 생성을 자동화할 수 있습니다.

### 자주 묻는 질문

#### Q1. .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 .NET 애플리케이션에서 프로그래밍 방식으로 Word 문서를 생성, 조작 및 저장할 수 있도록 하는 강력한 문서 처리 라이브러리입니다. 차트를 포함한 문서 요소로 단어 처리를 위한 광범위한 기능을 제공합니다.

#### Q2. .NET용 Aspose.Words를 어떻게 설치하나요?
Visual Studio의 NuGet 패키지 관리자를 사용하여 .NET용 Aspose.Words를 다운로드하여 설치할 수 있습니다. NuGet 패키지 관리자에서 "Apose.Words"를 검색하여 프로젝트에 설치하기만 하면 됩니다.

#### Q3. .NET용 Aspose.Words를 사용하여 차트의 다른 측면을 사용자 정의할 수 있나요?
예, Aspose.Words for .NET은 차트의 다양한 측면을 사용자 정의할 수 있는 광범위한 기능을 제공합니다. 축 속성을 정의하는 것 외에도 차트 유형, 데이터 계열, 범례, 제목, 그림 영역, 데이터 레이블 및 차트의 기타 여러 요소를 수정할 수 있습니다. API는 차트 모양과 동작을 세밀하게 제어할 수 있는 기능을 제공합니다.

#### Q4. .NET용 Aspose.Words를 사용하여 다양한 유형의 차트를 만들 수 있나요?
 예, Aspose.Words for .NET은 영역, 막대, 선, 원형, 분산형 등을 포함한 광범위한 차트 유형을 지원합니다. 당신은 사용할 수 있습니다`ChartType` Word 문서에 차트 모양을 삽입할 때 원하는 차트 유형을 지정하는 열거형입니다.

#### Q5. 차트를 다른 형식으로 저장할 수 있나요?
예, Aspose.Words for .NET을 사용하면 차트가 포함된 문서를 DOCX, PDF, HTML 등과 같은 다양한 형식으로 저장할 수 있습니다. 요구 사항에 따라 적절한 형식을 선택하고 사용할 수 있습니다.`Save` 의 방법`Document` 문서를 저장하는 개체입니다.

#### Q6. 문서의 여러 차트에 이러한 기술을 적용할 수 있나요?
 예, 각 차트에 대해 필요한 단계를 반복하여 문서의 여러 차트에 이러한 기술을 적용할 수 있습니다. 별도로 생성할 수 있습니다.`Chart` 그리고`ChartAxis` 각 차트의 개체를 선택하고 그에 따라 속성을 사용자 정의합니다. Aspose.Words for .NET은 단일 문서에서 여러 차트를 사용하여 단어 처리를 완벽하게 지원합니다.