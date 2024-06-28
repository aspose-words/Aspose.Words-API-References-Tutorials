---
title: Word 문서에 부동 이미지 삽입
linktitle: Word 문서에 부동 이미지 삽입
second_title: Aspose.Words 문서 처리 API
description: 자세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에 부동 이미지를 삽입하는 방법을 알아보세요. 문서를 향상시키는 데 적합합니다.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/insert-floating-image/
---
## 소개

텍스트를 보완하기 위해 이미지가 완벽하게 배치된 멋진 보고서나 제안서를 작성한다고 상상해 보십시오. .NET용 Aspose.Words를 사용하면 이를 쉽게 달성할 수 있습니다. 이 라이브러리는 문서 조작을 위한 강력한 기능을 제공하므로 개발자에게 적합한 솔루션입니다. 이 튜토리얼에서는 DocumentBuilder 클래스를 사용하여 플로팅 이미지를 삽입하는 방법에 중점을 둘 것입니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 가이드는 각 단계를 안내합니다.

## 전제조건

시작하기 전에 시작하는 데 필요한 모든 것이 갖추어져 있는지 확인하십시오.

1.  .NET용 Aspose.Words: 다음에서 라이브러리를 다운로드할 수 있습니다.[Aspose 릴리스 페이지](https://releases.aspose.com/words/net/).
2. Visual Studio: .NET 개발을 지원하는 모든 버전입니다.
3. C# 기본 지식: C# 프로그래밍의 기본을 이해하면 도움이 됩니다.
4. 이미지 파일: 로고, 그림 등 삽입하려는 이미지 파일입니다.

## 네임스페이스 가져오기

프로젝트에서 Aspose.Words를 사용하려면 필요한 네임스페이스를 가져와야 합니다. C# 파일 상단에 다음 줄을 추가하면 됩니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

이러한 전제조건과 네임스페이스가 준비되었으므로 튜토리얼을 시작할 준비가 되었습니다.

플로팅 이미지를 Word 문서에 삽입하는 과정을 관리 가능한 단계로 나누어 보겠습니다. 각 단계는 문제 없이 따라갈 수 있도록 자세히 설명됩니다.

## 1단계: 프로젝트 설정

먼저 Visual Studio에서 새 C# 프로젝트를 만듭니다. 단순화를 위해 콘솔 앱을 선택할 수 있습니다.

1. Visual Studio를 열고 새 프로젝트를 만듭니다.
2. "콘솔 앱(.NET Core)"을 선택하고 "다음"을 클릭합니다.
3. 프로젝트 이름을 지정하고 저장할 위치를 선택하세요. "만들기"를 클릭하세요.
4. NuGet 패키지 관리자를 통해 .NET용 Aspose.Words를 설치합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 "Apose.Words"를 검색하세요. 최신 버전을 설치하세요.

## 2단계: 문서 및 DocumentBuilder 초기화

이제 프로젝트가 설정되었으므로 Document 및 DocumentBuilder 개체를 초기화해 보겠습니다.

1.  새 인스턴스를 생성합니다.`Document` 수업:

```csharp
Document doc = new Document();
```

2. DocumentBuilder 객체를 초기화합니다.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

 그만큼`Document` 개체는 Word 문서를 나타내고`DocumentBuilder` 콘텐츠를 추가하는 데 도움이 됩니다.

## 3단계: 이미지 경로 정의

다음으로 이미지 파일의 경로를 지정합니다. 프로젝트 디렉터리에서 이미지에 액세스할 수 있는지 확인하세요.

이미지 디렉터리와 이미지 파일 이름을 정의합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imagePath = dataDir + "Transparent background logo.png";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 이미지가 저장된 실제 경로와 함께.

## 4단계: 플로팅 이미지 삽입

모든 설정이 완료되었으면 플로팅 이미지를 문서에 삽입해 보겠습니다.

 사용`InsertImage` 의 방법`DocumentBuilder` 이미지를 삽입하는 클래스:

```csharp
builder.InsertImage(imagePath,
   RelativeHorizontalPosition.Margin,
   100,
   RelativeVerticalPosition.Margin,
   100,
   200,
   100,
   WrapType.Square);
```

각 매개변수의 의미는 다음과 같습니다.
- `imagePath`이미지 파일의 경로입니다.
- `RelativeHorizontalPosition.Margin`: 여백을 기준으로 한 가로 위치입니다.
- `100`: 여백으로부터의 수평 오프셋(포인트)입니다.
- `RelativeVerticalPosition.Margin`: 여백을 기준으로 한 세로 위치입니다.
- `100`: 여백으로부터의 수직 오프셋(포인트)입니다.
- `200`: 이미지의 너비(포인트)입니다.
- `100`: 이미지의 높이(포인트)입니다.
- `WrapType.Square`: 이미지 주변의 텍스트 배치 스타일입니다.

## 5단계: 문서 저장

마지막으로 원하는 위치에 문서를 저장합니다.

1. 출력 파일 경로를 지정합니다.

```csharp
string outputPath = dataDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx";
```

2. 문서를 저장합니다:

```csharp
doc.Save(outputPath);
```

이제 부동 이미지가 포함된 Word 문서가 준비되었습니다!

## 결론

Aspose.Words for .NET을 사용하여 Word 문서에 부동 이미지를 삽입하는 작업은 관리 가능한 단계로 나누어 볼 때 매우 간단한 프로세스입니다. 이 가이드를 따르면 전문가 수준의 이미지를 문서에 추가하여 시각적 매력을 향상시킬 수 있습니다. Aspose.Words는 보고서, 제안서 또는 기타 문서 유형 작업 시 문서 조작을 쉽게 해주는 강력한 API를 제공합니다.

## FAQ

### .NET용 Aspose.Words를 사용하여 여러 이미지를 삽입할 수 있나요?

 예, 다음을 반복하여 여러 이미지를 삽입할 수 있습니다.`InsertImage` 원하는 매개변수를 사용하여 각 이미지에 대한 방법입니다.

### 이미지의 위치를 어떻게 변경하나요?

 당신은 조정할 수 있습니다`RelativeHorizontalPosition`, `RelativeVerticalPosition`, 오프셋 매개변수를 사용하여 필요에 따라 이미지 위치를 지정합니다.

### 이미지에 사용할 수 있는 다른 포장 유형은 무엇입니까?

 Aspose.Words는 다음과 같은 다양한 랩 유형을 지원합니다.`Inline`, `TopBottom`, `Tight`, `Through`, 그리고 더. 문서 레이아웃에 가장 적합한 것을 선택할 수 있습니다.

### 다른 이미지 형식을 사용할 수 있나요?

예, Aspose.Words는 JPEG, PNG, BMP 및 GIF를 포함한 광범위한 이미지 형식을 지원합니다.

### .NET용 Aspose.Words 무료 평가판을 받으려면 어떻게 해야 합니까?

 다음에서 무료 평가판을 받을 수 있습니다.[Aspose 무료 평가판 페이지](https://releases.aspose.com/).