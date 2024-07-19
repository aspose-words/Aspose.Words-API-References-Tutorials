---
title: 차트의 축에 대한 숫자 형식
linktitle: 차트의 축에 대한 숫자 형식
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 차트 축 번호의 형식을 지정하는 방법을 알아보세요. 문서의 가독성과 전문성을 쉽게 향상시킬 수 있습니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/number-format-for-axis/
---
## 소개

안녕하세요! 문서에서 차트 작업을 하면서 축의 숫자 서식을 지정하여 좀 더 전문적으로 보이도록 하고 싶었던 적이 있습니까? 글쎄, 당신은 운이 좋다! 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 이를 달성할 수 있는 방법에 대해 자세히 살펴보겠습니다. 이 강력한 라이브러리를 사용하면 파이처럼 쉬운 방식으로 Word 문서를 처리할 수 있습니다. 그리고 오늘 우리는 사용자 정의 숫자 형식을 사용하여 차트 축을 새롭게 바꾸는 데 중점을 두고 있습니다.

## 전제조건

시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오. 간단한 체크리스트는 다음과 같습니다.

-  .NET용 Aspose.Words: 설치되어 있는지 확인하세요. 그렇지 않다면 할 수 있습니다[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
- .NET Framework: 호환되는 .NET Framework가 설치되어 있는지 확인하세요.
- 개발 환경: Visual Studio와 같은 IDE는 완벽하게 작동합니다.
- C#에 대한 기본 지식: 코딩 예제를 따라가는 데 도움이 됩니다.

## 네임스페이스 가져오기

먼저, 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 이는 집을 짓기 전에 기초를 다지는 것과 같습니다. 코드 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Reporting;
```

이제 프로세스를 간단하고 따르기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 문서 설정

제목: 문서 초기화

먼저 새 문서와 문서 작성기를 만들어야 합니다. 이 단계는 걸작을 시작하기 전에 캔버스와 브러시를 준비하는 과정이라고 생각하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 여기,`dataDir` 최종 파일을 저장할 문서 디렉터리의 경로입니다.`Document`그리고`DocumentBuilder` Word 문서를 만들고 조작하는 데 도움이 되는 Aspose.Words의 클래스입니다.

## 2단계: 차트 삽입

제목: 문서에 차트 추가

다음으로 문서에 차트를 추가해 보겠습니다. 이것이 마법이 시작되는 곳입니다. 빈 캔버스 역할을 할 세로 막대형 차트를 삽입하겠습니다.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

 그만큼`InsertChart` 메서드는 지정된 유형(이 경우 열)의 차트와 차원을 문서에 삽입합니다.

## 3단계: 차트 시리즈 사용자 정의

표제: 차트를 데이터로 채우기

이제 차트에 일부 데이터를 추가해야 합니다. 이 단계는 차트를 의미 있는 정보로 채우는 것과 유사합니다.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

 여기에는 5개의 데이터 포인트가 있는 "Aspose Series 1"이라는 새 시리즈를 추가합니다. 그만큼`Series.Clear` 방법을 사용하면 새 시리즈를 추가하기 전에 기존 데이터가 제거됩니다.

## 4단계: 축 번호 형식 지정

제목: 축 번호를 아름답게 만드세요

마지막으로 Y축의 숫자 형식을 지정하여 더 쉽게 읽을 수 있도록 하겠습니다. 이는 마치 작품에 마무리 손질을 가하는 것과 같습니다.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

 그만큼`FormatCode` 속성을 사용하면 축의 숫자에 대한 사용자 지정 형식을 설정할 수 있습니다. 이 예에서는`#,##0`수천의 경우 큰 숫자가 쉼표와 함께 표시되도록 합니다.

## 5단계: 문서 저장

제목: 걸작을 저장하세요

이제 모든 설정이 완료되었으므로 문서를 저장할 차례입니다. 이 단계는 귀하의 작업을 크게 공개하는 단계입니다.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

 여기서는`Save` 메소드는 문서를 파일 이름으로 지정된 경로에 저장합니다.`WorkingWithCharts.NumberFormatForAxis.docx`.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 차트의 Y축 숫자 형식을 성공적으로 지정했습니다. 이렇게 하면 차트가 더욱 전문적으로 보일 뿐만 아니라 가독성도 향상됩니다. Aspose.Words는 프로그래밍 방식으로 멋진 Word 문서를 만드는 데 도움이 되는 다양한 기능을 제공합니다. 그렇다면 더 자세히 알아보고 그 밖에 무엇을 할 수 있는지 알아보세요.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 프로그래밍 방식으로 Word 문서를 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다.

### 축 번호 외에 차트의 다른 측면에 서식을 지정할 수 있나요?
전적으로! Aspose.Words for .NET을 사용하면 제목, 레이블의 형식을 지정하고 차트 모양을 사용자 정의할 수도 있습니다.

### .NET용 Aspose.Words에 대한 무료 평가판이 있습니까?
 예, 다음을 얻을 수 있습니다.[여기에서 무료 평가판](https://releases.aspose.com/).

### C# 외에 다른 .NET 언어와 함께 .NET용 Aspose.Words를 사용할 수 있나요?
예, Aspose.Words for .NET은 VB.NET 및 F#을 포함한 모든 .NET 언어와 호환됩니다.

### 더 자세한 문서는 어디서 찾을 수 있나요?
 자세한 문서는 다음에서 확인할 수 있습니다.[.NET 문서 페이지용 Aspose.Words](https://reference.aspose.com/words/net/).
