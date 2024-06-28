---
title: Word 문서에 영역형 차트 삽입
linktitle: Word 문서에 영역형 차트 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서에 영역 차트를 삽입하는 방법을 알아보세요. 계열 데이터를 추가하고 차트와 함께 문서를 저장합니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/insert-area-chart/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 영역 차트를 문서에 삽입하는 방법을 설명합니다. 제공된 소스 코드는 차트를 생성하고, 시리즈 데이터를 추가하고, 문서를 저장하는 방법을 보여줍니다.

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

 다음으로`InsertChart` 의 방법`DocumentBuilder` 문서에 영역형 차트를 삽입하려면

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트에 계열 데이터 추가

차트에 계열 데이터를 추가합니다. 이 예에서는 해당 날짜 및 값이 포함된 5개의 데이터 요소를 추가합니다.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## 4단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 영역 차트 삽입 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하는 삽입 영역 차트의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 영역 차트를 삽입하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 사용하면 새 문서를 만들고, 영역 차트를 삽입하고, 시리즈 데이터를 추가하고, 차트와 함께 문서를 저장할 수 있습니다.

Aspose.Words for .NET은 Word 문서의 차트를 사용하여 단어 처리를 위한 강력한 API를 제공합니다. 단 몇 줄의 코드만으로 전문가 수준의 영역 차트를 만들고 요구 사항에 따라 사용자 정의할 수 있습니다. 영역 차트는 일반적으로 시간이나 범주에 따른 데이터의 크기와 추세를 표시하는 데 사용됩니다.

.NET용 Aspose.Words를 사용하면 영역 차트가 포함된 문서 생성 프로세스를 자동화하여 수동 문서 생성에 드는 시간과 노력을 절약할 수 있습니다. 라이브러리는 다양한 차트 유형과 사용자 정의 옵션을 제공하므로 Word 문서에서 시각적으로 매력적이고 유익한 차트를 만들 수 있습니다.

### 자주 묻는 질문

#### Q1. .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 .NET 애플리케이션에서 프로그래밍 방식으로 Word 문서를 생성, 수정 및 변환할 수 있게 해주는 강력한 문서 처리 라이브러리입니다. 차트, 단락, 표 등을 포함한 문서 요소로 단어 처리를 위한 포괄적인 API 세트를 제공합니다.

#### Q2. .NET용 Aspose.Words를 어떻게 설치하나요?
.NET용 Aspose.Words를 설치하려면 Visual Studio의 NuGet 패키지 관리자를 사용하여 프로젝트에 라이브러리를 직접 설치할 수 있습니다. NuGet 패키지 관리자에서 "Apose.Words"를 검색하고 패키지를 설치하기만 하면 됩니다.

#### Q3. 영역 차트의 모양을 사용자 정의할 수 있나요?
예, .NET용 Aspose.Words를 사용하면 영역 차트 모양의 다양한 측면을 사용자 정의할 수 있습니다. 차트 제목, 계열 색상, 축 레이블, 차트 영역 서식 등의 속성을 수정할 수 있습니다. 라이브러리는 차트의 시각적 요소를 제어하고 필요에 맞는 사용자 정의된 모양을 생성할 수 있는 풍부한 API 세트를 제공합니다.

#### Q4. 영역 차트에 여러 계열을 추가할 수 있나요?
예, .NET용 Aspose.Words를 사용하여 영역 차트에 여러 시리즈를 추가할 수 있습니다. 각 계열은 차트에 표시되는 데이터 요소 집합을 나타냅니다. 다양한 데이터 세트가 포함된 시리즈를 추가하고 이름, 데이터 포인트 및 모양을 포함하여 각 시리즈를 개별적으로 사용자 정의할 수 있습니다.

#### Q5. 삽입된 영역형 차트가 포함된 문서를 다른 형식으로 저장할 수 있나요?
 예, Aspose.Words for .NET을 사용하면 삽입된 영역 차트가 포함된 문서를 DOCX, PDF, HTML 등과 같은 다양한 형식으로 저장할 수 있습니다. 요구 사항에 따라 원하는 출력 형식을 선택하고 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 문서를 저장하는 개체입니다. 삽입된 영역형 차트는 저장된 문서에 유지됩니다.

#### Q6. 영역 차트를 삽입한 후 데이터와 모양을 수정할 수 있나요?
예, 영역 차트를 문서에 삽입한 후 Aspose.Words for .NET에서 제공하는 API를 사용하여 해당 데이터와 모양을 수정할 수 있습니다. 계열 데이터를 업데이트하고, 차트 유형을 변경하고, 축 속성을 사용자 정의하고, 서식 옵션을 적용하여 Word 문서에서 동적 대화형 차트를 만들 수 있습니다.