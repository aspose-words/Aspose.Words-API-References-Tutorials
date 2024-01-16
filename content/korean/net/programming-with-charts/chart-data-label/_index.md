---
title: 차트 데이터 레이블 사용자 정의
linktitle: 차트 데이터 레이블 사용자 정의
second_title: Aspose.Words 문서 처리 API
description: 데이터 요소에 대한 추가 정보를 제공하기 위해 Aspose.Words for .NET을 사용하여 차트에 데이터 레이블을 추가하고 사용자 정의하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/chart-data-label/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트에 데이터 레이블을 추가하고 사용자 정의하는 방법을 설명합니다. 데이터 레이블은 차트의 데이터 요소에 대한 추가 정보를 제공합니다.

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

## 3단계: 차트 삽입 및 구성
 다음을 사용하여 문서에 차트를 삽입합니다.`InsertChart` 의 방법`DocumentBuilder` 물체. 원하는 차트 유형과 차원을 설정합니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## 4단계: 데이터 레이블 사용자 정의
차트 시리즈의 데이터 레이블 컬렉션에 액세스하고 다양한 속성을 수정하여 데이터 레이블의 모양을 사용자 정의합니다.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## 5단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithCharts.ChartDataLabel.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### .NET용 Aspose.Words를 사용하는 차트 데이터 레이블의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// 기본적으로 원형 차트의 데이터 요소에 데이터 레이블을 추가하면 다음과 같은 데이터 레이블에 지시선이 표시됩니다.
	// 데이터 포인트의 끝에서 멀리 떨어진 곳에 위치합니다. 지시선은 데이터 레이블과 해당 레이블 사이의 시각적 연결을 만듭니다.
	// 해당 데이터 포인트.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

그게 다야! Aspose.Words for .NET을 사용하여 차트에 데이터 레이블을 성공적으로 추가하고 사용자 정의했습니다.

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트에 데이터 레이블을 추가하고 사용자 정의하는 방법을 배웠습니다. 단계별 가이드에 따라 차트를 삽입하고, 데이터 레이블 컬렉션에 액세스하고, 속성을 수정하여 데이터 레이블의 모양을 사용자 지정할 수 있습니다. Aspose.Words for .NET은 Word 문서 및 차트를 사용하여 단어 처리를 위한 강력한 API를 제공하므로 사용자 정의된 데이터 레이블이 있는 시각적으로 매력적이고 유익한 차트를 만들 수 있습니다.

### 자주 묻는 질문

#### Q1. 차트의 데이터 레이블이란 무엇입니까?
차트의 데이터 레이블은 차트에 표시된 데이터 포인트에 대한 추가 정보를 제공합니다. 차트 유형 및 구성에 따라 값, 범주, 계열 이름, 백분율 또는 기타 관련 세부 정보를 표시할 수 있습니다.

#### Q2. 데이터 레이블의 모양을 사용자 정의할 수 있나요?
예, 차트의 데이터 레이블 모양을 맞춤설정할 수 있습니다. Aspose.Words for .NET은 범례 키, 지시선, 범주 이름, 시리즈 이름, 값 등과 같은 데이터 레이블의 다양한 속성을 수정하는 옵션을 제공합니다. 특정 요구 사항에 맞게 구분 기호를 설정하고 레이블 형식을 지정할 수도 있습니다.

#### Q3. 모든 차트 유형에 데이터 레이블을 추가할 수 있나요?
예, 막대 차트, 원형 차트, 선 차트 등을 포함한 다양한 유형의 차트에 데이터 레이블을 추가할 수 있습니다. 데이터 레이블을 추가하고 사용자 정의하는 과정은 차트 유형과 사용 중인 라이브러리 또는 도구에 따라 약간 다를 수 있습니다.
