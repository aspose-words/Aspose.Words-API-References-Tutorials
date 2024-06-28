---
title: Word 문서에 분산형 차트 삽입
linktitle: Word 문서에 분산형 차트 삽입
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 문서에 분산형 차트를 삽입하는 방법을 알아보세요. X 및 Y 좌표를 사용하여 계열 데이터를 추가합니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/insert-scatter-chart/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 분산형 차트를 문서에 삽입하는 방법을 설명합니다. 제공된 소스 코드는 차트를 생성하고, 시리즈 데이터를 추가하고, 문서를 저장하는 방법을 보여줍니다.

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

 다음으로`InsertChart` 의 방법`DocumentBuilder` 문서에 분산형 차트를 삽입하려면

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트에 계열 데이터 추가

차트에 계열 데이터를 추가합니다. 이 예에서는 두 개의 X 및 Y 좌표 세트를 추가합니다.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 4단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 분산형 차트를 삽입하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 분산형 차트 삽입에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 분산형 차트를 삽입하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 사용하면 새 문서를 만들고, 분산형 차트를 삽입하고, X 및 Y 좌표가 있는 계열 데이터를 추가하고, 차트와 함께 문서를 저장할 수 있습니다.

Aspose.Words for .NET은 Word 문서의 차트를 사용하여 단어 처리를 위한 포괄적인 API를 제공합니다. 분산형 차트는 두 개의 숫자 변수를 사용하여 데이터를 시각화하고 분석하는 데 유용합니다. Aspose.Words for .NET을 사용하면 X와 Y 값 사이의 관계를 나타내고 데이터의 패턴이나 추세를 식별하는 분산형 차트를 쉽게 만들 수 있습니다.

.NET용 Aspose.Words를 사용하면 분산형 차트로 문서 생성 프로세스를 자동화하여 수동 문서 생성에 드는 시간과 노력을 절약할 수 있습니다. 라이브러리는 분산형 차트를 포함하여 다양한 차트 유형을 제공하며 필요에 따라 차트 모양을 조정할 수 있는 다양한 사용자 정의 옵션을 제공합니다.

### 자주 묻는 질문

#### Q1. 분산형 차트란 무엇입니까?
분산형 차트는 두 숫자 변수 간의 관계를 표시하는 차트 유형입니다. 이는 좌표 격자에 표시된 일련의 점으로 구성되며, 하나의 변수는 X축에 표시되고 다른 변수는 Y축에 표시됩니다. 분산형 차트는 두 데이터 요소 집합 간의 패턴, 상관 관계 또는 추세를 식별하는 데 사용됩니다.

#### Q2. 분산형 차트에 여러 계열을 추가할 수 있나요?
예, .NET용 Aspose.Words를 사용하여 분산형 차트에 여러 계열을 추가할 수 있습니다. 각 계열은 해당 X 및 Y 좌표를 사용하여 데이터 요소 집합을 나타냅니다. 여러 시리즈를 추가하면 동일한 분산형 차트 내에서 다양한 데이터 세트를 비교 및 분석하여 데이터에 대한 포괄적인 보기를 제공할 수 있습니다.

#### Q3. 분산형 차트의 모양을 맞춤설정할 수 있나요?
예, .NET용 Aspose.Words를 사용하면 분산형 차트 모양의 다양한 측면을 사용자 정의할 수 있습니다. 계열 색상, 표식 모양, 축 레이블, 차트 영역 서식 등의 속성을 수정할 수 있습니다. 라이브러리는 차트의 시각적 요소를 제어하고 필요에 맞는 사용자 정의된 모양을 생성할 수 있는 풍부한 API 세트를 제공합니다.

#### Q4. 분산형 차트가 삽입된 문서를 다른 형식으로 저장할 수 있나요?
예, Aspose.Words for .NET을 사용하면 DOCX, PDF, HTML 등과 같은 다양한 형식으로 분산형 차트가 삽입된 문서를 저장할 수 있습니다. 요구 사항에 따라 원하는 출력 형식을 선택하고 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 문서를 저장하는 개체입니다. 삽입된 분산형 차트는 저장된 문서에 유지됩니다.

#### Q5. 분산형 차트를 삽입한 후 데이터와 모양을 수정할 수 있나요?
예, 문서에 분산형 차트를 삽입한 후 Aspose.Words for .NET에서 제공하는 API를 사용하여 해당 데이터와 모양을 수정할 수 있습니다. 새로운 X 및 Y 좌표로 계열 데이터를 업데이트하고, 표식 모양과 색상을 변경하고, 축 속성을 사용자 정의하고, 서식 옵션을 적용하여 Word 문서에서 동적 대화형 차트를 만들 수 있습니다.