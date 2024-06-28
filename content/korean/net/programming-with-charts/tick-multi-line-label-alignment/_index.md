---
title: 차트에서 여러 줄 레이블 정렬을 선택합니다.
linktitle: 차트에서 여러 줄 레이블 정렬을 선택합니다.
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 차트 축에서 눈금 여러 줄 레이블을 정렬하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-charts/tick-multi-line-label-alignment/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트 축에서 눈금 여러 줄 레이블의 정렬을 설정하는 방법을 설명합니다. 제공된 소스 코드는 차트를 만들고, 축에 액세스하고, 눈금 레이블 정렬을 수정하는 방법을 보여줍니다.

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
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## 3단계: 눈금 레이블 정렬 설정

 눈금 여러 줄 레이블의 정렬을 설정하려면`AxisX` 차트의 속성을 설정하고`TickLabelAlignment` 속성을 원하는 정렬로 설정합니다. 이 예에서는 정렬을 다음과 같이 설정합니다.`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## 4단계: 문서 저장

 마지막으로 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 눈금 여러 줄 레이블 정렬 설정 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용한 Tick Multi Line Label Alignment의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// 이 속성은 여러 줄 레이블에만 적용됩니다.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 차트 축에서 눈금 여러 줄 레이블 정렬을 설정하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하여 새 문서를 만들고, 분산형 차트를 삽입하고, 차트 축에 액세스하고, 눈금 레이블 정렬을 수정할 수 있습니다.

Aspose.Words for .NET은 Word 문서의 차트를 조작할 수 있는 강력한 기능을 제공합니다. 여러 줄 레이블을 선택하면 축 레이블에 여러 줄에 걸쳐 줄바꿈하거나 분할해야 하는 긴 텍스트가 포함된 경우 유용합니다. 눈금 레이블 정렬을 설정하면 차트 축 내에서 여러 줄 레이블의 가로 정렬을 제어하여 최적의 프레젠테이션과 가독성을 보장할 수 있습니다.

눈금 여러 줄 레이블 정렬을 사용자 정의하면 특히 길거나 복잡한 레이블을 처리할 때 차트의 모양을 미세 조정할 수 있습니다. 레이블을 오른쪽, 왼쪽, 중앙 또는 양쪽 정렬로 정렬하면 축을 따라 눈금 레이블이 균형있고 시각적으로 매력적인 배열을 얻을 수 있습니다.

Aspose.Words for .NET을 사용하면 차트 축의 눈금 레이블 정렬 속성에 쉽게 액세스하고 수정할 수 있으므로 Word 문서 차트에서 눈금 레이블의 모양과 레이아웃을 완전히 제어할 수 있습니다.

### 자주 묻는 질문

#### Q1. 차트 축의 눈금 여러 줄 레이블은 무엇입니까?
차트 축의 여러 줄 레이블을 선택하면 레이블 텍스트가 길거나 사용 가능한 공간에 맞게 줄 바꿈이 필요한 경우 여러 줄에 걸쳐 표시되는 축 레이블을 나타냅니다. 레이블 텍스트를 자르거나 시각적으로 복잡하게 만드는 대신 차트 축은 가독성을 보장하기 위해 레이블을 자동으로 여러 줄로 분할합니다. 여러 줄 레이블을 선택하면 차트에서 긴 범주 또는 값 레이블을 처리할 때 특히 유용합니다.

#### Q2. 차트 축에서 눈금 레이블 정렬을 사용자 정의할 수 있나요?
 예, Aspose.Words for .NET을 사용하여 차트 축의 눈금 레이블 정렬을 사용자 정의할 수 있습니다. 액세스하여`TickLabelAlignment` 의 재산`ChartAxis` 개체의 경우 눈금 레이블에 대해 원하는 정렬을 설정할 수 있습니다. 정렬 옵션에는 왼쪽, 오른쪽, 가운데 또는 양쪽 정렬이 포함됩니다. 정렬을 조정하면 차트 축을 따라 눈금 레이블의 수평 위치를 제어하여 적절한 가독성과 시각적 표현을 보장할 수 있습니다.

#### Q3. 차트 축의 눈금 레이블 정렬 변경을 언제 고려해야 합니까?
최적의 표시와 가독성이 필요한 길거나 여러 줄의 레이블이 있는 경우 차트 축의 눈금 레이블 정렬을 변경하는 것이 좋습니다. 정렬을 조정하면 레이블이 겹치거나 잘리지 않고 적절하게 정렬되고 간격이 지정되도록 할 수 있습니다. 긴 범주 이름, 자세한 값 레이블이 있는 차트 또는 기본 정렬이 원하는 시각적 모양을 제공하지 않는 기타 시나리오를 처리할 때 눈금 레이블 정렬을 변경하는 것을 고려하십시오.

#### Q4. 눈금 레이블 정렬이 차트 축의 한 줄 레이블에 영향을 줍니까?
아니요. 눈금 레이블 정렬 속성은 차트 축의 한 줄 레이블에 영향을 주지 않습니다. 포장이나 분할이 필요한 여러 줄의 라벨용으로 특별히 설계되었습니다. 한 줄 레이블은 차트 축의 기본 정렬 설정에 따라 정렬됩니다. 눈금 레이블 정렬 속성은 여러 줄에 걸쳐 있는 레이블에만 적용되므로 여러 줄 레이블 내에서 각 줄의 정렬을 제어할 수 있습니다.

#### Q5. 차트의 X축과 Y축에 대해 눈금 레이블을 다르게 정렬할 수 있나요?
 예, Aspose.Words for .NET을 사용하여 차트의 X축과 Y축에 대해 눈금 레이블을 다르게 정렬할 수 있습니다. 눈금 레이블 정렬 속성은 각 차트 축에 따라 다릅니다. 해당에 접속하여`ChartAxis` X축 또는 Y축에 대한 개체의 경우 눈금 레이블 정렬을 다른 값으로 독립적으로 설정할 수 있습니다. 이를 통해 차트의 각 축에 대한 특정 요구 사항에 따라 눈금 레이블을 다르게 정렬할 수 있는 유연성이 제공됩니다.