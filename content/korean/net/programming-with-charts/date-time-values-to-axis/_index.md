---
title: 차트 축에 날짜 시간 값 추가
linktitle: 차트 축에 날짜 시간 값 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 차트 축에 날짜 시간 값을 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/date-time-values-to-axis/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트 축에 날짜 시간 값을 추가하는 방법을 설명합니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 문서 및 DocumentBuilder 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder`문서 작업에 사용할 개체입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 차트 모양 삽입 및 구성
 다음을 사용하여 문서에 차트 모양을 삽입합니다.`InsertChart` 의 방법`DocumentBuilder` 물체. 원하는 차트 유형과 차원을 설정합니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## 4단계: 차트에 데이터 추가
날짜 시간 값을 포함하여 차트 시리즈에 데이터를 추가합니다.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## 5단계: 축 구성
날짜 시간 값을 표시하도록 차트의 X축을 구성합니다.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## 6단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithCharts.DateTimeValuesToAxis.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### .NET용 Aspose.Words를 사용하여 날짜 시간 값을 축으로 변환하는 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// 주요 단위를 일주일로, 보조 단위를 하루로 설정합니다.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

이 예제 코드는 새 Word 문서를 만들고 X축에 날짜 시간 값이 있는 세로 막대형 차트를 삽입한 다음 문서를 지정된 디렉터리에 저장합니다.

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트 축에 날짜 시간 값을 추가하는 방법을 배웠습니다. 단계별 가이드에 따라 차트를 만들고, 계열에 날짜 시간 값을 추가하고, 날짜 시간 값을 정확하게 표시하도록 축을 구성할 수 있습니다. Aspose.Words for .NET은 Word 문서의 차트를 사용하여 단어 처리를 위한 강력한 기능 세트를 제공하므로 날짜 시간 값으로 데이터를 효과적으로 표현하고 시각화할 수 있습니다.

### 자주 묻는 질문

#### Q1. .NET용 Aspose.Words를 사용하여 차트 축에 날짜 시간 값을 추가할 수 있나요?
예, .NET용 Aspose.Words를 사용하면 Word 문서의 차트 축에 날짜 시간 값을 추가하고 표시할 수 있습니다. Aspose.Words는 축의 날짜 시간 값 처리를 포함하여 다양한 차트 유형으로 작업하고 모양을 사용자 정의할 수 있는 API와 기능을 제공합니다.

#### Q2. 차트 시리즈에 날짜 시간 값을 어떻게 추가합니까?
 차트 시리즈에 날짜 시간 값을 추가하려면 다음을 사용할 수 있습니다.`Add`차트 시리즈의 방법. 해당 계열 값과 함께 날짜 시간 값의 배열을 범주(X축) 데이터로 제공합니다. 이를 통해 차트에 날짜 시간 값이 포함된 데이터 포인트를 그릴 수 있습니다.

#### Q3. 날짜 시간 값을 표시하도록 축을 구성하려면 어떻게 해야 합니까?
 적절한 속성을 설정하여 날짜 시간 값을 표시하도록 차트 축을 구성할 수 있습니다. 예를 들어, 다음을 사용하여 축의 최소값과 최대값을 지정할 수 있습니다.`Scaling.Minimum` 그리고`Scaling.Maximum` 각각 속성. 또한 주요 단위와 보조 단위를 설정하여 축의 간격과 눈금 표시를 정의할 수 있습니다.
