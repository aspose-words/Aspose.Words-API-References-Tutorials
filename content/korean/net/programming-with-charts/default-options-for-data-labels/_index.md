---
title: 차트의 데이터 레이블에 대한 기본 옵션 설정
linktitle: 차트의 데이터 레이블에 대한 기본 옵션 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 차트의 데이터 레이블에 대한 기본 옵션을 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/default-options-for-data-labels/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 데이터 레이블에 대한 기본 옵션을 설정하는 방법을 설명합니다. 제공된 코드는 Aspose.Words를 사용하여 차트를 만들고, 데이터 시리즈를 추가하고, 데이터 레이블을 사용자 정의하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

시작하기 전에 다음 요구 사항이 충족되었는지 확인하세요.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다. NuGet 패키지 관리자를 사용하여 다운로드하여 설치할 수 있습니다.
- 출력 문서가 저장될 문서 디렉터리 경로입니다.

## 2단계: 새 문서 만들기 및 차트 삽입

 먼저 새로 만들어 보겠습니다.`Document` 객체와`DocumentBuilder` 문서를 작성합니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 다음으로, 다음을 사용하여 문서에 차트를 삽입합니다.`InsertChart` 의 방법`DocumentBuilder`. 이 예에서는 원형 차트를 삽입하겠습니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트에 데이터 계열 추가

이제 차트에 데이터 계열을 추가해 보겠습니다. 이 예에서는 세 가지 범주와 해당 값을 추가합니다.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## 4단계: 데이터 레이블 사용자 정의

 차트의 데이터 레이블을 사용자 정의하려면`ChartDataLabelCollection` 시리즈와 관련된 개체입니다.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 그런 다음 다양한 속성을 수정할 수 있습니다.`labels`데이터 레이블에 대해 원하는 옵션을 설정하는 개체입니다. 이 예에서는 백분율과 값 표시를 활성화하고 지시선을 비활성화하며 사용자 정의 구분 기호를 설정합니다.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## 5단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 차트의 데이터 레이블에 대한 기본 옵션 설정 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하는 데이터 레이블의 기본 옵션에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 데이터 레이블에 대한 기본 옵션을 설정하는 방법을 배웠습니다. 단계별 가이드에 따라 차트를 만들고, 데이터 시리즈를 추가하고, 특정 요구 사항에 맞게 데이터 레이블을 사용자 지정할 수 있습니다. Aspose.Words for .NET은 Word 문서의 차트를 사용하여 단어 처리를 위한 강력한 API를 제공하므로 다양한 차트 요소를 조작하고 원하는 모양과 기능을 얻을 수 있습니다.

 속성을 설정하여`ChartDataLabelCollection`차트 시리즈와 연결된 개체를 사용하면 백분율, 값, 지시선 및 사용자 정의 구분 기호 표시와 같은 옵션을 포함하여 데이터 레이블 표시를 제어할 수 있습니다. 이러한 유연성을 통해 데이터를 효과적으로 표현하고 차트의 시각적 표현을 향상시킬 수 있습니다.

### 자주 묻는 질문

#### Q1. .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 .NET 애플리케이션을 사용하여 프로그래밍 방식으로 Word 문서를 생성, 조작 및 저장할 수 있도록 하는 라이브러리입니다. 차트를 포함한 문서 요소로 단어 처리를 위한 광범위한 기능을 제공합니다.

#### Q2. .NET용 Aspose.Words를 어떻게 설치하나요?
Visual Studio에서 NuGet 패키지 관리자를 사용하여 .NET용 Aspose.Words를 다운로드하여 설치할 수 있습니다. NuGet 패키지 관리자에서 "Aspose.Words"를 검색하여 프로젝트에 설치하기만 하면 됩니다.

#### Q3. .NET용 Aspose.Words를 사용하여 차트의 다른 측면을 사용자 정의할 수 있나요?
예, Aspose.Words for .NET을 사용하면 차트 유형, 축 레이블, 범례, 플롯 영역 등과 같은 차트의 다양한 측면을 사용자 정의할 수 있습니다. 차트 개체의 다양한 속성에 액세스하고 수정하여 원하는 모양과 동작을 얻을 수 있습니다.

#### Q4. 차트를 다른 형식으로 저장할 수 있나요?
 예, Aspose.Words for .NET은 차트가 포함된 문서를 DOCX, PDF, HTML 등을 포함한 다양한 형식으로 저장할 수 있도록 지원합니다. 요구 사항에 따라 적절한 형식을 선택하고 사용할 수 있습니다.`Save` 의 방법`Document` 문서를 저장하는 개체입니다.

#### Q5. 이러한 기술을 다른 차트 유형에 적용할 수 있나요?
예, 이 튜토리얼에서 설명하는 기술은 Aspose.Words for .NET에서 지원하는 다른 차트 유형에 적용될 수 있습니다. 핵심은 단어 처리에 사용되는 차트 유형과 관련된 관련 개체 및 속성에 액세스하는 것입니다.