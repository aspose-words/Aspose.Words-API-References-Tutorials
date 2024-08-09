---
title: 부동 테이블 위치
linktitle: 부동 테이블 위치
second_title: Aspose.Words 문서 처리 API
description: 자세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 테이블의 부동 위치를 제어하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/floating-table-position/
---
## 소개

.NET용 Aspose.Words를 사용하여 Word 문서에서 테이블 위치를 조작하는 세계로 뛰어들 준비가 되셨습니까? 버클을 채우세요. 오늘은 테이블의 부동 위치를 쉽게 제어하는 방법을 알아볼 것이기 때문입니다. 당신을 즉시 테이블 위치 지정 마법사로 바꿔드리겠습니다!

## 전제 조건

이 흥미진진한 여정을 시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인합시다.

1. .NET 라이브러리용 Aspose.Words: 최신 버전이 있는지 확인하세요. 그렇지 않으면,[여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
2. .NET Framework: 개발 환경이 .NET으로 설정되어 있는지 확인하세요.
3. 개발 환경: Visual Studio 또는 선호하는 IDE.
4. Word 문서: 표가 포함된 Word 문서를 준비합니다.

## 네임스페이스 가져오기

시작하려면 .NET 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. C# 파일 상단에 포함할 코드 조각은 다음과 같습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Tables;
```

## 단계별 가이드

이제 프로세스를 간단하고 이해하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 문서 로드

가장 먼저, Word 문서를 로드해야 합니다. 이곳이 귀하의 테이블이 위치한 곳입니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Word 문서가 캔버스이고 테이블이 그 위에 있는 예술 작품이라고 상상해 보세요. 우리의 목표는 이 작품을 캔버스에서 원하는 위치에 정확히 배치하는 것입니다.

## 2단계: 테이블에 액세스

다음으로 문서 내의 테이블에 액세스해야 합니다. 일반적으로 문서 본문의 첫 번째 테이블을 사용하여 작업하게 됩니다.

```csharp
Table table = doc.FirstSection.Body.Tables[0];
```

이 단계를 실제 문서에서 작업하려는 테이블을 찾는 것으로 생각하십시오. 변경하려면 해당 위치를 정확히 알아야 합니다.

## 3단계: 수평 위치 설정

이제 테이블의 수평 위치를 설정해 보겠습니다. 이는 테이블이 문서의 왼쪽 가장자리에서 얼마나 멀리 배치되는지를 결정합니다.

```csharp
table.AbsoluteHorizontalDistance = 10;
```

 문서 전체에서 테이블을 수평으로 이동하는 것으로 시각화하세요. 그만큼`AbsoluteHorizontalDistance` 왼쪽 가장자리로부터의 정확한 거리입니다.

## 4단계: 수직 정렬 설정

또한 테이블의 수직 정렬도 설정해야 합니다. 이렇게 하면 테이블이 주변 텍스트 내에서 수직으로 가운데에 배치됩니다.

```csharp
table.RelativeVerticalAlignment = VerticalAlignment.Center;
```

벽에 그림을 걸어놓는다고 상상해 보세요. 미적인 매력을 위해 세로 중앙에 위치하도록 해야 합니다. 이 단계에서는 이를 달성합니다.

## 5단계: 수정된 문서 저장

마지막으로 테이블 위치를 지정한 후 수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

이는 편집한 문서에서 '저장'을 누르는 것과 같습니다. 이제 모든 변경 사항이 보존됩니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서에서 테이블의 부동 위치를 제어하는 방법을 마스터했습니다. 이러한 기술을 사용하면 테이블을 완벽하게 배치하여 문서의 가독성과 미적 특성을 향상시킬 수 있습니다. .NET용 Aspose.Words의 방대한 기능을 계속 실험하고 탐색해 보세요.

## FAQ

### 페이지 상단에서 테이블까지의 수직 거리를 설정할 수 있나요?

 예, 다음을 사용할 수 있습니다.`AbsoluteVerticalDistance` 페이지 상단 가장자리에서 테이블까지의 수직 거리를 설정하는 속성입니다.

### 문서 오른쪽에 표를 정렬하려면 어떻게 해야 하나요?

 테이블을 오른쪽으로 정렬하려면`HorizontalAlignment` 테이블의 속성`HorizontalAlignment.Right`.

### 동일한 문서에서 여러 테이블을 다르게 배치할 수 있습니까?

 전적으로! 다음을 반복하여 여러 테이블의 위치에 개별적으로 액세스하고 설정할 수 있습니다.`Tables` 문서에 수집합니다.

### 수평 정렬에 상대 위치 지정을 사용할 수 있습니까?

예, Aspose.Words는 다음과 같은 속성을 사용하여 수평 및 수직 정렬 모두에 대한 상대 위치 지정을 지원합니다.`RelativeHorizontalAlignment`.

### Aspose.Words는 문서의 여러 섹션에서 부동 테이블을 지원합니까?

예, 문서 내의 특정 섹션과 해당 테이블에 액세스하여 부동 테이블을 다른 섹션에 배치할 수 있습니다.