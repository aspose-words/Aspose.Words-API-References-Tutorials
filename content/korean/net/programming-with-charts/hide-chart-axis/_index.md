---
title: Word 문서에서 차트 축 숨기기
linktitle: Word 문서에서 차트 축 숨기기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서에서 차트 축을 숨기는 방법을 알아보세요. 보다 명확하고 집중된 차트 표시를 위해 축을 숨깁니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/hide-chart-axis/
---

이 튜토리얼에서는 문서에서 차트 축을 숨기기 위해 .NET용 Aspose.Words를 사용하는 방법을 설명합니다. 제공된 소스 코드는 차트를 만들고, 계열 데이터를 추가하고, 차트 축을 숨기는 방법을 보여줍니다.

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

 다음으로,`InsertChart` 의 방법`DocumentBuilder`. 이 예에서는 세로 막대형 차트를 삽입해 보겠습니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트에 계열 데이터 추가

차트에 계열 데이터를 추가합니다. 이 예에서는 5개의 항목과 해당 값을 추가하겠습니다.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 4단계: 차트 축 숨기기

 차트 축을 숨기려면`AxisY` 차트의 속성을 설정하고`Hidden`재산`true`.

```csharp
chart.AxisY.Hidden = true;
```

이 예에서는 차트의 Y축을 숨깁니다.

## 5단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 차트 축 숨기기 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 차트 축 숨기기에 대한 예제 소스 코드 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 차트 축을 숨기는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 사용하여 차트를 만들고, 계열 데이터를 추가하고, 차트 축을 숨겨 원하는 시각적 효과를 얻을 수 있습니다.

 Aspose.Words for .NET은 Word 문서의 차트를 사용하여 단어 처리를 위한 포괄적인 API를 제공하므로 축 속성을 포함하여 차트의 다양한 측면을 조작할 수 있습니다. 액세스하여`AxisY` 차트 속성의 경우 Y축을 숨겨 차트 시각화에서 제거할 수 있습니다.

축 선과 레이블로 인해 주의가 산만해지지 않고 차트 데이터에 집중하려는 경우 차트 축을 숨기는 것이 유용할 수 있습니다. 차트에 더욱 깔끔하고 미니멀한 모양을 제공합니다.

.NET용 Aspose.Words를 사용하면 차트 작성 기능을 .NET 애플리케이션에 쉽게 통합하고 사용자 정의된 차트와 숨겨진 차트 축을 사용하여 전문가 수준의 문서를 생성할 수 있습니다.

### 자주 묻는 질문

#### Q1. .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 .NET 애플리케이션에서 프로그래밍 방식으로 Word 문서를 생성, 조작 및 저장할 수 있도록 하는 강력한 문서 처리 라이브러리입니다. 차트 및 차트 축을 포함한 문서 요소를 사용하여 단어 처리를 위한 광범위한 기능을 제공합니다.

#### Q2. .NET용 Aspose.Words를 어떻게 설치하나요?
Visual Studio의 NuGet 패키지 관리자를 사용하여 .NET용 Aspose.Words를 다운로드하여 설치할 수 있습니다. NuGet 패키지 관리자에서 "Aspose.Words"를 검색하여 프로젝트에 설치하기만 하면 됩니다.

#### Q3. 차트의 X축과 Y축을 모두 숨길 수 있나요?
 예, Aspose.Words for .NET을 사용하여 차트의 X축과 Y축을 모두 숨길 수 있습니다. X축을 숨기려면`AxisX` 차트의 속성을 설정하고`Hidden`재산`true` . 마찬가지로 Y축을 숨기려면`AxisY` 속성을 설정하고`Hidden`재산`true`. 이를 통해 차트 시각화에서 두 축을 모두 제거할 수 있습니다.

#### Q4. 축을 숨긴 후 다시 표시할 수 있나요?
예, Aspose.Words for .NET을 사용하여 숨긴 후 차트 축을 다시 표시할 수 있습니다. 숨겨진 축을 표시하려면 간단히`Hidden` 해당 속성`AxisX` 또는`AxisY` 반대하다`false`. 그러면 차트에 축이 다시 표시됩니다.

#### Q5. 차트 축의 다른 속성을 사용자 지정할 수 있나요?
 예, Aspose.Words for .NET을 사용하면 축 제목, 레이블, 선 색상 등과 같은 차트 축의 다양한 속성을 사용자 정의할 수 있습니다. 액세스하여`AxisX` 그리고`AxisY` 차트의 속성을 수정하려면 다음과 같은 속성을 수정할 수 있습니다.`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, 그리고 많은 다른 사람들. 이를 통해 차트 축의 모양과 동작을 세밀하게 제어할 수 있습니다.

#### Q6. 숨겨진 축이 있는 차트를 다른 파일 형식으로 저장할 수 있나요?
 예, Aspose.Words for .NET을 사용하면 숨겨진 축이 있는 차트가 포함된 문서를 DOCX, PDF, HTML 등과 같은 다양한 파일 형식으로 저장할 수 있습니다. 요구 사항에 따라 원하는 출력 형식을 선택하고 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 문서를 저장하는 개체입니다. 숨겨진 축은 저장된 문서에 유지됩니다.