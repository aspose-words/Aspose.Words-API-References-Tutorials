---
title: 모양을 사용하여 차트 생성 및 사용자 정의
linktitle: 모양을 사용하여 차트 생성 및 사용자 정의
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에서 도형을 사용하여 차트를 만들고 사용자 정의하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/create-chart-using-shape/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 도형을 사용하여 차트를 만드는 방법을 설명합니다.

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
 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 문서 작업에 사용할 개체입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 차트 모양 삽입 및 구성
 다음을 사용하여 문서에 차트 모양을 삽입합니다.`InsertChart` 의 방법`DocumentBuilder` 물체. 원하는 차트 유형과 차원을 설정합니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 4단계: 차트 사용자 정의
차트 제목, 범례 등 다양한 속성을 수정하여 차트를 맞춤설정하세요.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## 5단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithCharts.CreateChartUsingShape.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### .NET용 Aspose.Words를 사용하여 모양을 사용하여 차트 만들기에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// 제목 텍스트로 null 또는 빈 값을 지정하면 자동 생성된 제목이 표시됩니다.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

그게 다야! Aspose.Words for .NET을 사용하여 Word 문서의 모양을 사용하여 차트를 성공적으로 만들었습니다.

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 도형을 사용하여 차트를 만드는 방법을 배웠습니다. 단계별 안내에 따라 차트 모양을 삽입 및 구성하고, 모양을 사용자 지정하고, 문서를 저장할 수 있습니다. Aspose.Words for .NET은 Word 문서 및 차트를 사용한 단어 처리를 위한 포괄적인 기능 세트를 제공하므로 .NET 응용 프로그램에서 직접 전문적이고 시각적으로 매력적인 차트를 만들 수 있습니다.

### 자주 묻는 질문

#### Q1. .NET용 Aspose.Words를 사용하여 Word 문서에서 차트를 만들 수 있나요?
예, .NET용 Aspose.Words를 사용하면 프로그래밍 방식으로 Word 문서에 차트를 만들 수 있습니다. Aspose.Words는 다양한 유형의 차트를 삽입하고, 모양을 사용자 정의하고, 차트 데이터를 조작할 수 있는 API와 기능을 제공합니다.

#### Q2. .NET용 Aspose.Words는 어떤 차트 유형을 지원합니까?
Aspose.Words for .NET은 선형 차트, 막대 차트, 원형 차트, 영역 차트, 분산형 차트 등을 포함한 광범위한 차트 유형을 지원합니다. 데이터 및 시각화 요구 사항에 따라 적절한 차트 유형을 선택할 수 있습니다.

#### Q3. 생성된 차트의 모양을 맞춤설정할 수 있나요?
예, Aspose.Words for .NET을 사용하여 생성된 차트의 모양을 사용자 정의할 수 있습니다. 특정 디자인 및 서식 요구 사항에 맞게 차트 제목, 범례 위치, 데이터 레이블, 축 레이블, 색상 및 기타 시각적 요소와 같은 속성을 수정할 수 있습니다.
