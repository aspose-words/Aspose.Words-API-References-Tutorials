---
title: Word 문서에 간단한 기둥형 차트 삽입
linktitle: Word 문서에 간단한 기둥형 차트 삽입
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 문서에 간단한 세로 막대형 차트를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/insert-simple-column-chart/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 간단한 세로 막대형 차트를 문서에 삽입하는 방법을 설명합니다. 제공된 소스 코드는 차트를 생성하고, 시리즈 데이터를 추가하고, 문서를 저장하는 방법을 보여줍니다.

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

 다음으로`InsertChart` 의 방법`DocumentBuilder` 문서에 세로 막대형 차트를 삽입하려면 요구 사항에 따라 다양한 차트 유형과 크기를 지정할 수 있습니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트에 계열 데이터 추가

차트에 계열 데이터를 추가합니다. 이 예에서는 각각 두 개의 범주가 있는 여러 시리즈를 추가합니다.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## 4단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 간단한 세로 막대형 차트를 삽입하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 간단한 기둥형 차트 삽입에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// 다양한 차트 유형과 크기를 지정할 수 있습니다.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// 기본 생성된 시리즈를 삭제합니다.
	seriesColl.Clear();
	// 카테고리 이름 배열을 만듭니다. 이 튜토리얼에는 두 개의 카테고리가 있습니다.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// 데이터 배열은 비어 있어서는 안 되며 배열의 크기가 동일해야 합니다.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 간단한 세로 막대형 차트를 삽입하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 사용하면 새 문서를 만들고, 세로 막대형 차트를 삽입하고, 카테고리와 해당 값이 포함된 여러 시리즈를 추가하고, 차트와 함께 문서를 저장할 수 있습니다.

Aspose.Words for .NET은 Word 문서의 차트를 사용하여 단어 처리를 위한 강력하고 유연한 API를 제공합니다. 간단한 세로 막대형 차트는 다양한 범주의 데이터를 표현하고 비교하는 효과적인 방법입니다. Aspose.Words for .NET을 사용하면 사용자 정의 데이터로 세로 막대형 차트를 쉽게 만들고, 시각적 비교를 위해 여러 시리즈를 추가하고, 요구 사항에 따라 차트 모양을 사용자 정의할 수 있습니다.

.NET용 Aspose.Words를 사용하면 세로 막대형 차트가 포함된 문서 생성 프로세스를 자동화하여 수동 문서 생성에 드는 시간과 노력을 절약할 수 있습니다. 라이브러리는 간단한 기둥형 차트를 포함하여 다양한 차트 유형을 제공하며 필요에 맞게 차트 모양을 조정할 수 있는 다양한 사용자 정의 옵션을 제공합니다.

### 자주 묻는 질문

#### Q1. 세로 막대형 차트란 무엇입니까?
세로 막대형 차트는 다양한 높이의 세로 막대를 사용하여 데이터를 표시하는 차트 유형입니다. 각 열은 범주를 나타내며 열의 높이는 해당 범주의 값에 해당합니다. 기둥형 차트는 일반적으로 다양한 범주의 데이터를 비교하거나 시간에 따른 변화를 추적하는 데 사용됩니다.

#### Q2. 세로 막대형 차트에 여러 시리즈를 추가할 수 있나요?
예, .NET용 Aspose.Words를 사용하면 세로 막대형 차트에 여러 시리즈를 추가할 수 있습니다. 각 계열은 해당 범주와 값이 포함된 데이터 요소 집합을 나타냅니다. 여러 시리즈를 추가하면 동일한 세로 막대형 차트 내에서 다양한 데이터 세트를 비교 및 분석하여 데이터에 대한 포괄적인 보기를 제공할 수 있습니다.

#### Q3. 기둥형 차트의 모양을 사용자 정의할 수 있나요?
예, Aspose.Words for .NET을 사용하면 세로 막대형 차트 모양의 다양한 측면을 사용자 정의할 수 있습니다. 계열 색상, 축 레이블, 데이터 레이블 및 차트 영역 서식과 같은 속성을 수정할 수 있습니다. 라이브러리는 차트의 시각적 요소를 제어하고 필요에 맞는 사용자 정의된 모양을 생성할 수 있는 풍부한 API 세트를 제공합니다.

#### Q4. 삽입된 세로 막대형 차트가 포함된 문서를 다른 형식으로 저장할 수 있나요?
 예, Aspose.Words for .NET을 사용하면 삽입된 세로 막대형 차트가 포함된 문서를 DOCX, PDF, HTML 등과 같은 다양한 형식으로 저장할 수 있습니다. 요구 사항에 따라 원하는 출력 형식을 선택하고 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 문서를 저장하는 개체입니다. 삽입된 세로 막대형 차트는 저장된 문서에 유지됩니다.

#### Q5. 컬럼 차트를 삽입한 후 데이터 및 모양을 수정할 수 있나요?
예, 문서에 세로 막대형 차트를 삽입한 후 Aspose.Words for .NET에서 제공하는 API를 사용하여 해당 데이터와 모양을 수정할 수 있습니다. 새로운 범주와 값으로 계열 데이터를 업데이트하고, 열의 색상과 서식을 변경하고, 축 속성을 사용자 지정하고, 다양한 서식 옵션을 적용하여 Word 문서에서 시각적으로 매력적인 동적 차트를 만들 수 있습니다.