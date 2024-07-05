---
title: Word 문서의 단락에 테두리 및 음영 적용
linktitle: Word 문서의 단락에 테두리 및 음영 적용
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 단락에 테두리와 음영을 적용합니다. 문서 형식을 향상하려면 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
## 소개

안녕하세요. 멋진 테두리와 음영을 사용하여 Word 문서를 돋보이게 만드는 방법이 궁금하신가요? 글쎄, 당신은 바로 이곳에 있어요! 오늘 우리는 문단을 멋지게 만들기 위해 .NET용 Aspose.Words의 세계로 뛰어들고 있습니다. 단 몇 줄의 코드만으로 문서가 전문 디자이너의 작업처럼 매끄럽게 보이는 것을 상상해 보십시오. 시작할 준비가 되셨나요? 갑시다!

## 전제조건

소매를 걷어붙이고 코딩을 시작하기 전에 필요한 모든 것이 있는지 확인합시다. 빠른 체크리스트는 다음과 같습니다.

-  .NET용 Aspose.Words: 이 라이브러리를 설치해야 합니다. 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio 또는 .NET을 지원하는 기타 IDE.
- C#에 대한 기본 지식: 코드 조각을 이해하고 조정하는 데 충분합니다.
- 유효한 라이센스:[임시면허](https://purchase.aspose.com/temporary-license/) 또는 에서 구입한 것[Aspose](https://purchase.aspose.com/buy).

## 네임스페이스 가져오기

코드를 시작하기 전에 필요한 네임스페이스를 프로젝트로 가져왔는지 확인해야 합니다. 이를 통해 Aspose.Words의 모든 멋진 기능에 접근할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System.Drawing;
```

이제 프로세스를 작은 단계로 나누어 보겠습니다. 각 단계에는 제목과 자세한 설명이 있습니다. 준비가 된? 갑시다!

## 1단계: 문서 디렉토리 설정

먼저, 아름다운 형식의 문서를 저장할 장소가 필요합니다. 문서 디렉터리의 경로를 설정해 보겠습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 이 디렉토리는 최종 문서가 저장되는 곳입니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 컴퓨터의 실제 경로와 함께.

## 2단계: 새 문서 및 DocumentBuilder 만들기

 다음으로 새 문서와`DocumentBuilder` 물체. 그만큼`DocumentBuilder` 문서를 조작할 수 있게 해주는 마술 지팡이입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 그만큼`Document` 개체는 전체 Word 문서를 나타내며`DocumentBuilder` 콘텐츠를 추가하고 형식을 지정하는 데 도움이 됩니다.

## 3단계: 단락 테두리 정의

이제 단락에 세련된 테두리를 추가해 보겠습니다. 텍스트와의 거리를 정의하고 다양한 테두리 스타일을 설정하겠습니다.

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

여기서는 텍스트와 테두리 사이의 거리를 20포인트로 설정했습니다. 모든 측면(왼쪽, 오른쪽, 위쪽, 아래쪽)의 테두리가 이중선으로 설정됩니다. 멋지죠?

## 4단계: 단락에 음영 적용

테두리는 훌륭하지만 약간의 음영을 사용하여 한 단계 더 발전시켜 보겠습니다. 단락을 돋보이게 하기 위해 색상이 혼합된 대각선 십자 패턴을 사용하겠습니다.

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

이번 단계에서는 밝은 산호색을 배경색으로 하고 밝은 연어색을 전경색으로 한 대각선 크로스 텍스처를 적용했습니다. 단락에 디자이너 옷을 입히는 것과 같습니다!

## 5단계: 단락에 텍스트 추가

텍스트가 없는 단락은 무엇입니까? 서식 지정이 어떻게 작동하는지 확인하기 위해 샘플 문장을 추가해 보겠습니다.

```csharp
builder.Write("I'm a formatted paragraph with double border and nice shading.");
```

이 줄은 텍스트를 문서에 삽입합니다. 단순하지만 이제는 세련된 프레임과 음영 처리된 배경으로 포장되었습니다.

## 6단계: 문서 저장

마지막으로 작업을 저장할 시간입니다. 설명적인 이름을 사용하여 지정된 디렉터리에 문서를 저장해 보겠습니다.

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

 그러면 문서가 다음 이름으로 저장됩니다.`DocumentFormatting.ApplyBordersAndShadingToParagraph.doc` 앞서 지정한 디렉토리에 있습니다.

## 결론

그리고 거기에 있습니다! 단 몇 줄의 코드만으로 평범한 단락을 시각적으로 매력적인 콘텐츠로 변환했습니다. Aspose.Words for .NET을 사용하면 문서에 전문적인 서식을 매우 쉽게 추가할 수 있습니다. 보고서, 편지 또는 어떤 문서를 준비하든 이 요령은 좋은 인상을 남기는 데 도움이 될 것입니다. 지금 바로 사용해보시고 문서가 생생하게 살아나는 모습을 지켜보세요!

## FAQ

### 각 테두리에 서로 다른 선 스타일을 사용할 수 있나요?  
 전적으로! .NET용 Aspose.Words를 사용하면 각 테두리를 개별적으로 사용자 정의할 수 있습니다. 그냥 설정하세요`LineStyle` 가이드에 표시된 대로 각 테두리 유형에 대해

### 다른 어떤 음영 텍스처를 사용할 수 있나요?  
 단색, 가로 줄무늬, 세로 줄무늬 등 사용할 수 있는 여러 텍스처가 있습니다. 을 체크 해봐[Aspose 문서](https://reference.aspose.com/words/net/) 전체 목록을 보려면.

### 테두리 색상을 어떻게 변경할 수 있나요?  
 다음을 사용하여 테두리 색상을 설정할 수 있습니다.`Color` 각 테두리에 대한 속성입니다. 예를 들어,`borders[BorderType.Left].Color = Color.Red;`.

### 텍스트의 특정 부분에 테두리와 음영을 적용할 수 있나요?  
 예. 다음을 사용하여 특정 텍스트 실행에 테두리와 음영을 적용할 수 있습니다.`Run` 내의 개체`DocumentBuilder`.

### 여러 단락에 대해 이 프로세스를 자동화할 수 있나요?  
분명히! 프로그래밍 방식으로 단락을 반복하고 동일한 테두리 및 음영 설정을 적용할 수 있습니다.
