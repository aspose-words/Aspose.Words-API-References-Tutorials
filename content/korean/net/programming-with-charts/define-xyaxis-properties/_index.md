---
title: 차트에서 XY 축 속성 정의
linktitle: 차트에서 XY 축 속성 정의
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 차트에서 XY 축 속성을 정의하는 방법을 알아보세요. .NET 개발자에게 적합합니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/define-xyaxis-properties/
---
## 소개

차트는 데이터를 시각화하는 강력한 도구입니다. 동적 차트가 포함된 전문적인 문서를 작성해야 할 때 Aspose.Words for .NET은 매우 귀중한 라이브러리입니다. 이 문서에서는 Aspose.Words for .NET을 사용하여 차트에서 XY 축 속성을 정의하는 과정을 안내하고 명확성과 이해 용이성을 보장하기 위해 각 단계를 세분화합니다.

## 전제조건

코딩을 시작하기 전에 갖춰야 할 몇 가지 전제 조건이 있습니다.

1. .NET용 Aspose.Words: .NET용 Aspose.Words 라이브러리가 있는지 확인하세요. 당신은 할 수 있습니다[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio와 같은 통합 개발 환경(IDE)이 필요합니다.
3. .NET Framework: 개발 환경이 .NET 개발용으로 설정되어 있는지 확인하세요.
4. C# 기본 지식: 이 가이드에서는 사용자가 C# 프로그래밍에 대한 기본 지식을 가지고 있다고 가정합니다.

## 네임스페이스 가져오기

우선 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 이를 통해 문서와 차트를 생성하고 조작하는 데 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

프로세스를 간단한 단계로 나누어 각 단계는 차트에서 XY 축 속성을 정의하는 특정 부분에 중점을 둡니다.

## 1단계: 문서 및 DocumentBuilder 초기화

 먼저 새 문서를 초기화해야 합니다.`DocumentBuilder` 물체. 그만큼`DocumentBuilder` 문서에 내용을 삽입하는 데 도움이 됩니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 차트 삽입

다음으로 문서에 차트를 삽입합니다. 이 예에서는 영역 차트를 사용합니다. 필요에 따라 차트의 차원을 사용자 정의할 수 있습니다.

```csharp
// 차트 삽입
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 기본 계열 지우기 및 사용자 정의 데이터 추가

기본적으로 차트에는 미리 정의된 시리즈가 있습니다. 이를 지우고 사용자 정의 데이터 시리즈를 추가하겠습니다.

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

## 4단계: X축 속성 정의

이제 X축의 속성을 정의할 차례입니다. 여기에는 범주 유형 설정, 축 교차 사용자 정의, 눈금 표시 및 레이블 조정이 포함됩니다.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //Y축의 표시 단위(백)로 측정됩니다.
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## 5단계: Y축 속성 정의

마찬가지로 Y축의 속성도 설정합니다. 여기에는 눈금 레이블 위치, 주요 및 보조 단위, 표시 단위 및 배율 설정이 포함됩니다.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## 6단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장합니다. 그러면 사용자 정의된 차트가 포함된 Word 문서가 생성됩니다.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## 결론

관련 단계를 이해하면 Aspose.Words for .NET을 사용하여 Word 문서에서 차트를 만들고 사용자 정의하는 것은 간단합니다. 이 가이드에서는 문서 초기화부터 최종 제품 저장까지 차트에서 XY 축 속성을 정의하는 과정을 안내했습니다. 이러한 기술을 사용하면 문서를 향상시키는 상세하고 전문적인 차트를 만들 수 있습니다.

## FAQ

### Aspose.Words for .NET으로 어떤 유형의 차트를 만들 수 있나요?
영역, 막대, 선, 원형 등 다양한 유형의 차트를 만들 수 있습니다.

### .NET용 Aspose.Words를 어떻게 설치하나요?
 .NET용 Aspose.Words는 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/) 제공된 설치 지침을 따르십시오.

### 내 차트의 모양을 사용자 정의할 수 있나요?
예, .NET용 Aspose.Words를 사용하면 색상, 글꼴, 축 속성을 포함하여 차트를 광범위하게 사용자 정의할 수 있습니다.

### .NET용 Aspose.Words에 대한 무료 평가판이 있습니까?
 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/).

### 더 많은 튜토리얼과 문서는 어디서 찾을 수 있나요?
 다음에서 더 많은 튜토리얼과 자세한 문서를 찾을 수 있습니다.[.NET 문서 페이지용 Aspose.Words](https://reference.aspose.com/words/net/).
