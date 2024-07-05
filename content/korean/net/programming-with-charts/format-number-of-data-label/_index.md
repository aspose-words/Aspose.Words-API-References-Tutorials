---
title: 차트의 데이터 레이블 형식 수
linktitle: 차트의 데이터 레이블 형식 수
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 차트의 데이터 레이블 수 형식을 지정하는 방법을 알아보세요. 데이터 레이블의 숫자 형식을 쉽게 사용자 정의합니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/format-number-of-data-label/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 데이터 레이블 수 형식을 지정하는 방법을 설명합니다. 제공된 소스 코드는 차트를 만들고, 계열 데이터를 추가하고, 데이터 레이블의 숫자 형식을 사용자 지정하는 방법을 보여줍니다.

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

 다음으로,`InsertChart` 의 방법`DocumentBuilder`. 이 예에서는 꺾은선형 차트를 삽입하겠습니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## 3단계: 차트에 계열 데이터 추가

차트에 계열 데이터를 추가합니다. 이 예에서는 세 가지 범주와 해당 값을 추가합니다.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## 4단계: 데이터 레이블의 숫자 형식 사용자 지정

 데이터 레이블 수의 형식을 지정하려면`DataLabels` 시리즈와 관련된 컬렉션입니다.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

이 예에서는 각 데이터 레이블에 대해 서로 다른 숫자 형식을 설정합니다. 첫 번째 데이터 레이블은 통화로 형식화되고, 두 번째는 날짜로, 세 번째는 백분율로 지정됩니다.

## 5단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 차트의 데이터 레이블 수 형식 지정 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하는 데이터 레이블 형식 번호의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// 기본 생성된 시리즈를 삭제합니다.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// 또는 소스 셀에 연결되도록 서식 코드를 설정할 수 있습니다.
	//이 경우 NumberFormat은 일반으로 재설정되고 소스 셀에서 상속됩니다.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트의 데이터 레이블 수 형식을 지정하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 사용하여 차트를 만들고, 계열 데이터를 추가하고, 요구 사항에 따라 데이터 레이블의 숫자 형식을 사용자 지정할 수 있습니다.

 Aspose.Words for .NET은 Word 문서의 차트를 사용하여 단어 처리를 위한 포괄적인 API를 제공하므로 데이터 레이블을 포함하여 차트의 다양한 측면을 조작할 수 있습니다. 액세스하여`DataLabels` 시리즈와 연결된 컬렉션을 사용하면 개별 데이터 레이블의 숫자 형식을 사용자 정의할 수 있습니다.

API를 사용하면 값 표시를 제어하고, 각 데이터 레이블에 대해 서로 다른 숫자 형식을 설정하고, 숫자 형식을 소스 셀에 연결할 수 있습니다. 이러한 유연성을 통해 통화 기호, 날짜 형식, 백분율 값 등 원하는 형식으로 숫자 데이터를 차트에 표시할 수 있습니다.

.NET용 Aspose.Words를 사용하면 강력한 차트 작성 기능을 .NET 애플리케이션에 통합하고 완전한 형식의 차트와 데이터 레이블이 포함된 전문가 수준의 문서를 생성할 수 있습니다.

### 자주 묻는 질문

#### Q1. .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 .NET 애플리케이션에서 프로그래밍 방식으로 Word 문서를 생성, 조작 및 저장할 수 있도록 하는 기능이 풍부한 문서 처리 라이브러리입니다. 차트 및 데이터 레이블을 포함한 문서 요소를 사용하여 단어 처리를 위한 광범위한 기능을 제공합니다.

#### Q2. .NET용 Aspose.Words를 어떻게 설치하나요?
Visual Studio의 NuGet 패키지 관리자를 사용하여 .NET용 Aspose.Words를 다운로드하여 설치할 수 있습니다. NuGet 패키지 관리자에서 "Aspose.Words"를 검색하여 프로젝트에 설치하기만 하면 됩니다.

#### Q3. .NET용 Aspose.Words를 사용하여 차트의 다른 측면에 서식을 지정할 수 있나요?
예, Aspose.Words for .NET은 차트의 다양한 측면에 서식을 지정하기 위한 광범위한 기능을 제공합니다. 데이터 레이블 외에도 차트 유형, 계열 데이터, 축 속성, 범례, 제목, 그림 영역 및 차트의 기타 여러 요소를 사용자 정의할 수 있습니다. API는 차트 모양과 서식을 세밀하게 제어할 수 있는 기능을 제공합니다.

#### Q4. 동일한 계열의 서로 다른 데이터 레이블에 서로 다른 숫자 형식을 적용할 수 있나요?
예, Aspose.Words for .NET을 사용하면 동일한 시리즈 내의 개별 데이터 레이블에 다양한 숫자 형식을 적용할 수 있습니다. 액세스하여`DataLabels` 시리즈와 연결된 컬렉션의 경우`FormatCode` 각 데이터 레이블의 속성을 사용하여 원하는 숫자 형식을 지정합니다. 이를 통해 동일한 차트 내에서 다양한 형식으로 숫자 값을 표시할 수 있습니다.

#### Q5. 데이터 레이블에 사용자 정의 숫자 형식을 사용할 수 있습니까?
 예, .NET용 Aspose.Words는 데이터 레이블에 대한 사용자 정의 숫자 형식을 지원합니다. 설정을 통해 원하는 숫자 형식을 지정할 수 있습니다.`FormatCode` 데이터 레이블의 속성을 사용자 정의 형식 코드로 변환합니다. 이를 통해 통화 기호, 날짜 형식, 백분율 값 등과 같은 다양한 숫자 형식을 유연하게 적용할 수 있습니다.

#### Q6. 서식이 지정된 데이터 레이블이 있는 차트를 다른 형식으로 저장할 수 있나요?
예, Aspose.Words for .NET을 사용하면 DOCX, PDF, HTML 등과 같은 다양한 형식의 서식 있는 데이터 레이블이 있는 차트가 포함된 문서를 저장할 수 있습니다. 요구 사항에 따라 적절한 형식을 선택하고 사용할 수 있습니다.`Save` 의 방법`Document` 문서를 저장하는 개체입니다. 서식이 지정된 데이터 레이블은 저장된 문서에 유지됩니다.