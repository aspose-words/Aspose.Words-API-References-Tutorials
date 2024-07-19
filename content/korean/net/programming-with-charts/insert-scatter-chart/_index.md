---
title: Word 문서에 분산형 차트 삽입
linktitle: Word 문서에 분산형 차트 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word에 분산형 차트를 삽입하는 방법을 알아보세요. 시각적 데이터 표현을 문서에 통합하는 쉬운 단계입니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/insert-scatter-chart/
---
## 소개

이 튜토리얼에서는 .NET용 Aspose.Words를 활용하여 Word 문서에 분산형 차트를 삽입하는 방법을 배웁니다. 분산형 차트는 두 가지 변수를 기반으로 데이터 포인트를 효과적으로 표시하여 문서를 더욱 매력적이고 유익하게 만들 수 있는 강력한 시각적 도구입니다.

## 전제조건

.NET용 Aspose.Words를 사용하여 분산형 차트를 만들기 전에 다음 전제 조건이 있는지 확인하세요.

1.  .NET용 Aspose.Words 설치: 다음에서 .NET용 Aspose.Words를 다운로드하여 설치하세요.[여기](https://releases.aspose.com/words/net/).
   
2. C#에 대한 기본 지식: C# 프로그래밍 언어 및 .NET 프레임워크에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

시작하려면 C# 프로젝트에서 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
```

이제 Aspose.Words for .NET을 사용하여 Word 문서에 분산형 차트를 삽입하는 과정을 자세히 살펴보겠습니다.

## 1단계: 문서 및 DocumentBuilder 초기화

 먼저, 새 인스턴스를 초기화합니다.`Document` 수업과`DocumentBuilder` 문서 작성을 시작하는 클래스입니다.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 분산형 차트 삽입

 사용`InsertChart` 의 방법`DocumentBuilder` 문서에 분산형 차트를 삽입하는 클래스입니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 3단계: 차트에 데이터 계열 추가

이제 분산형 차트에 데이터 시리즈를 추가하세요. 이 예에서는 특정 데이터 요소가 있는 계열을 추가하는 방법을 보여줍니다.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 4단계: 문서 저장

 마지막으로 다음을 사용하여 수정된 문서를 원하는 위치에 저장합니다.`Save` 의 방법`Document` 수업.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## 결론

축하해요! Aspose.Words for .NET을 사용하여 Word 문서에 분산형 차트를 삽입하는 방법을 성공적으로 배웠습니다. 분산형 차트는 데이터 관계를 시각화하는 훌륭한 도구이며 Aspose.Words를 사용하면 이를 문서에 쉽게 통합하여 명확성과 이해도를 높일 수 있습니다.

## FAQ

### Aspose.Words를 사용하여 분산형 차트의 모양을 사용자 정의할 수 있나요?
예, Aspose.Words를 사용하면 색상, 축 및 레이블과 같은 차트 속성을 광범위하게 사용자 정의할 수 있습니다.

### Aspose.Words는 다른 버전의 Microsoft Word와 호환됩니까?
Aspose.Words는 다양한 버전의 Microsoft Word를 지원하여 플랫폼 간 호환성을 보장합니다.

### Aspose.Words는 다른 유형의 차트를 지원합니까?
예, Aspose.Words는 막대 차트, 선 차트, 원형 차트를 포함한 광범위한 차트 유형을 지원합니다.

### 분산형 차트의 데이터를 프로그래밍 방식으로 동적으로 업데이트할 수 있나요?
물론 Aspose.Words API 호출을 사용하여 차트 데이터를 동적으로 업데이트할 수 있습니다.

### Aspose.Words에 대한 추가 지원이나 지원은 어디서 받을 수 있나요?
 추가 지원을 받으려면 다음을 방문하세요.[Aspose.Words 지원 포럼](https://forum.aspose.com/c/words/8).