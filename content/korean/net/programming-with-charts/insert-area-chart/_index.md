---
title: Word 문서에 영역형 차트 삽입
linktitle: Word 문서에 영역형 차트 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서에 영역 차트를 삽입하는 방법을 알아보세요. 계열 데이터를 추가하고 차트와 함께 문서를 저장합니다.
type: docs
weight: 10
url: /ko/net/programming-with-charts/insert-area-chart/
---
## 소개

.NET용 Aspose.Words를 사용하여 Word 문서에 영역 차트를 삽입하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 튜토리얼은 Word 문서에서 멋지고 유익한 영역 차트를 만들기 위해 알아야 할 모든 것을 안내합니다. 전제 조건을 다루고, 필요한 네임스페이스를 가져오는 방법을 보여주고, 명확하고 따르기 쉬운 지침을 통해 프로세스의 각 단계를 안내합니다.

## 전제조건

시작하기 전에 시작하는 데 필요한 모든 것이 갖추어져 있는지 확인하십시오.

1.  .NET용 Aspose.Words: .NET용 Aspose.Words가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/words/net/).
2. .NET Framework: 컴퓨터에 .NET Framework가 설치되어 있는지 확인하세요.
3. IDE: 코드를 작성하고 실행하기 위한 Visual Studio와 같은 IDE(통합 개발 환경)입니다.
4. 기본 C# 지식: C# 프로그래밍에 대한 기본적인 이해가 도움이 됩니다.

이러한 필수 구성 요소가 준비되면 Word 문서에서 아름다운 영역 차트를 만들 준비가 된 것입니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이러한 네임스페이스는 Aspose.Words for .NET에서 Word 문서 및 차트 작업에 필요한 클래스와 메서드를 제공합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

이제 필수 네임스페이스를 가져왔으므로 문서 생성 및 영역 차트 삽입을 단계별로 진행하겠습니다.

## 1단계: 새 Word 문서 만들기

새 Word 문서를 만드는 것부터 시작해 보겠습니다. 이것이 영역 차트를 삽입할 기반이 됩니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 이 단계에서는 새로운 것을 초기화합니다.`Document` Word 문서를 나타내는 개체입니다.

## 2단계: DocumentBuilder를 사용하여 차트 삽입

 다음으로 우리는`DocumentBuilder` 문서에 영역 차트를 삽입하는 클래스입니다.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 여기서는`DocumentBuilder` 개체를 사용하여 특정 크기(432x252)의 영역 차트를 문서에 삽입합니다.

## 3단계: 차트 개체에 액세스

 차트를 삽입한 후`Chart` 영역 차트를 사용자 정의하는 개체입니다.

```csharp
Chart chart = shape.Chart;
```

 이 코드 줄은`Chart` 방금 삽입한 모양의 개체입니다.

## 4단계: 차트에 계열 데이터 추가

이제 차트에 일부 데이터를 추가할 차례입니다. 날짜와 해당 값이 포함된 계열을 추가하겠습니다.

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

이 단계에서는 날짜 집합과 해당 값이 포함된 "Aspose Series 1"이라는 시리즈를 추가합니다.

## 5단계: 문서 저장

마지막으로 삽입된 영역 차트와 함께 문서를 저장하겠습니다.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

이 코드 줄은 문서를 지정된 파일 이름으로 지정된 디렉터리에 저장합니다.

## 결론

축하해요! .NET용 Aspose.Words를 사용하여 Word 문서에 영역 차트를 성공적으로 삽입했습니다. 이 가이드에서는 환경 설정부터 최종 문서 저장까지 각 단계를 안내했습니다. .NET용 Aspose.Words를 사용하면 Word 문서에 다양한 차트와 기타 복잡한 요소를 만들어 보고서와 프레젠테이션을 더욱 역동적이고 유익하게 만들 수 있습니다.

## FAQ

### 다른 .NET 언어와 함께 .NET용 Aspose.Words를 사용할 수 있나요?
예, .NET용 Aspose.Words는 VB.NET과 같은 다른 .NET 언어를 지원합니다.

### 차트의 모양을 사용자 정의할 수 있나요?
전적으로! Aspose.Words for .NET은 차트의 모양을 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.

### 단일 Word 문서에 여러 차트를 추가할 수 있나요?
예, 단일 Word 문서에 필요한 만큼 차트를 삽입할 수 있습니다.

### .NET용 Aspose.Words는 다른 차트 유형을 지원합니까?
예, Aspose.Words for .NET은 막대, 선, 원형 등을 포함한 다양한 차트 유형을 지원합니다.

### .NET용 Aspose.Words의 임시 라이선스는 어디서 구할 수 있나요?
 임시면허를 취득하실 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).