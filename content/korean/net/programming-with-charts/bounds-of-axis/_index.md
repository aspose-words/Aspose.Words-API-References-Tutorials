---
title: 차트의 축 경계
linktitle: 차트의 축 경계
second_title: Aspose.Words 문서 처리 API
description: 축에 표시되는 값의 범위를 제어하는 .NET용 Aspose.Words를 사용하여 차트에서 축의 경계를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/bounds-of-axis/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트에서 축 경계를 설정하는 방법을 설명합니다. 차트를 삽입하고, 계열 데이터를 추가하고, 축 배율을 구성하여 축의 최소값과 최대값을 정의할 수 있습니다.

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

## 3단계: 차트 삽입 및 구성
 다음을 사용하여 문서에 차트를 삽입합니다.`InsertChart` 의 방법`DocumentBuilder` 물체. 원하는 차트 유형과 차원을 설정합니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 4단계: 계열 데이터 추가
차트에서 기존 계열을 지우고 새 계열 데이터를 추가합니다. 이 예에서는 "항목 1"이라는 레이블이 있는 계열을 "항목 5"와 해당 값에 추가합니다.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 5단계: 축 경계 설정
 다음을 사용하여 최소값과 최대값을 설정하여 Y축의 배율을 구성합니다.`Scaling.Minimum` 그리고`Scaling.Maximum` 축의 속성입니다.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## 6단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithCharts.BoundsOfAxis.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### .NET용 Aspose.Words를 사용하는 Bounds Of Axis의 예제 소스 코드 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 차트의 축 경계를 성공적으로 설정했습니다.

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트에서 축 경계를 설정하는 방법을 배웠습니다. 단계별 가이드에 따라 차트를 삽입 및 구성하고, 계열 데이터를 추가하고, 축 배율에 대한 최소값과 최대값을 정의할 수 있습니다. Aspose.Words for .NET은 Word 문서의 단어 처리를 위한 강력하고 유연한 API를 제공하므로 동적이고 시각적으로 매력적인 차트를 쉽게 만들 수 있습니다.


### 자주 묻는 질문

#### Q1. .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 프로그래밍 방식으로 Word 문서를 작업할 수 있게 해주는 라이브러리입니다. Word 문서를 작성, 조작 및 저장하기 위한 다양한 기능을 제공합니다.

#### Q2. .NET용 Aspose.Words를 어떻게 설치하나요?
.NET용 Aspose.Words를 설치하려면 Visual Studio에서 NuGet 패키지 관리자를 사용할 수 있습니다. NuGet 패키지 관리자에서 "Aspose.Words"를 검색하여 프로젝트에 설치하기만 하면 됩니다.

#### Q3. 다른 프로그래밍 언어와 함께 .NET용 Aspose.Words를 사용할 수 있나요?
아니요, Aspose.Words for .NET은 .NET 애플리케이션용으로 특별히 설계되었습니다. C# 및 VB.NET과 같은 프로그래밍 언어에서 작동합니다.

#### Q4. .NET용 Aspose.Words를 사용하기 위한 다른 전제 조건이 있나요?
.NET용 Aspose.Words 라이브러리를 설치하는 것 외에도 C# 프로그래밍 및 Word 문서를 사용한 단어 처리에 대한 기본 지식이 있어야 합니다. .NET 프레임워크에 익숙해지는 것도 도움이 됩니다.
