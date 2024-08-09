---
title: 가로 세로 비율이 잠겼습니다.
linktitle: 가로 세로 비율이 잠겼습니다.
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 도형의 가로 세로 비율을 잠그는 방법을 알아보세요. 이미지와 모양의 균형을 유지하려면 이 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/aspect-ratio-locked/
---
## 소개

Word 문서에서 이미지와 모양의 완벽한 비율을 유지하는 방법이 궁금하신가요? 경우에 따라 크기를 조정할 때 이미지와 모양이 왜곡되지 않도록 해야 합니다. 여기에서 종횡비를 잠그는 것이 유용합니다. 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 도형의 종횡비를 설정하는 방법을 살펴보겠습니다. 우리는 이를 따라하기 쉬운 단계로 나누어 이러한 기술을 자신있게 프로젝트에 적용할 수 있도록 하겠습니다.

## 전제 조건

코드를 살펴보기 전에 시작하는 데 필요한 사항을 살펴보겠습니다.

- .NET용 Aspose.Words 라이브러리: .NET용 Aspose.Words가 설치되어 있어야 합니다. 아직 하지 않았다면 다음을 수행할 수 있습니다.[여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
- 개발 환경: .NET 개발 환경이 설정되어 있는지 확인하세요. Visual Studio는 널리 사용되는 선택입니다.
- C#에 대한 기본 지식: C# 프로그래밍에 어느 정도 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이러한 네임스페이스를 통해 Word 문서 및 도형 작업에 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 1단계: 문서 디렉토리 설정

 모양 조작을 시작하기 전에 문서가 저장될 디렉터리를 설정해야 합니다. 단순화를 위해 자리 표시자를 사용하겠습니다.`YOUR DOCUMENT DIRECTORY`. 이를 문서 디렉터리의 실제 경로로 바꾸세요.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 문서 만들기

다음으로 Aspose.Words를 사용하여 새 Word 문서를 만듭니다. 이 문서는 모양과 이미지를 추가하기 위한 캔버스 역할을 합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 여기서는 인스턴스를 생성합니다.`Document` 수업을 듣고`DocumentBuilder` 문서 콘텐츠를 구축하는 데 도움이 됩니다.

## 3단계: 이미지 삽입

 이제 문서에 이미지를 삽입해 보겠습니다. 우리는`InsertImage` 의 방법`DocumentBuilder`수업. 지정된 디렉터리에 이미지가 있는지 확인하세요.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 바꾸다`dataDir + "Transparent background logo.png"` 이미지 파일의 경로와 함께.

## 4단계: 종횡비 잠금

이미지가 삽입되면 이미지 비율을 잠글 수 있습니다. 종횡비를 잠그면 크기를 조정할 때 이미지의 비율이 일정하게 유지됩니다.

```csharp
shape.AspectRatioLocked = true;
```

 환경`AspectRatioLocked` 에게`true` 이미지가 원래의 종횡비를 유지하는지 확인합니다.

## 5단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장합니다. 이 단계에서는 문서 파일에 대한 모든 변경 사항을 기록합니다.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## 결론

축하해요! .NET용 Aspose.Words를 사용하여 Word 문서에서 도형의 종횡비를 설정하는 방법을 성공적으로 배웠습니다. 다음 단계를 따르면 이미지와 모양이 비율을 유지하여 문서를 전문적이고 세련되게 만들 수 있습니다. 다양한 이미지와 모양을 자유롭게 실험하여 다양한 시나리오에서 종횡비 잠금 기능이 어떻게 작동하는지 확인하세요.

## FAQ

### 화면비를 잠근 후 잠금을 해제할 수 있나요?
예, 설정을 통해 종횡비 잠금을 해제할 수 있습니다.`shape.AspectRatioLocked = false`.

### 가로 세로 비율이 고정된 이미지의 크기를 조정하면 어떻게 되나요?
이미지는 원래 너비 대 높이 비율을 유지하면서 비례적으로 크기가 조정됩니다.

### 이미지 외에 다른 도형에도 적용할 수 있나요?
전적으로! 종횡비 잠금 기능은 직사각형, 원 등을 포함한 모든 모양에 적용할 수 있습니다.

### .NET용 Aspose.Words는 .NET Core와 호환됩니까?
예, .NET용 Aspose.Words는 .NET Framework와 .NET Core를 모두 지원합니다.

### .NET용 Aspose.Words에 대한 추가 문서는 어디서 찾을 수 있나요?
 포괄적인 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/words/net/).