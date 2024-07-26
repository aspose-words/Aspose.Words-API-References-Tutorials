---
title: JPEG 페이지 범위 가져오기
linktitle: JPEG 페이지 범위 가져오기
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 사용자 정의 설정을 사용하여 Word 문서의 특정 페이지를 JPEG로 변환합니다. 밝기, 대비, 해상도를 단계별로 조정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---
## 소개

축소판을 만들거나, 온라인으로 문서를 미리 보거나, 보다 접근하기 쉬운 형식으로 콘텐츠를 공유할 때 Word 문서를 이미지로 변환하는 것은 매우 유용할 수 있습니다. Aspose.Words for .NET을 사용하면 밝기, 대비, 해상도와 같은 다양한 설정을 사용자 정의하면서 Word 문서의 특정 페이지를 JPEG 형식으로 쉽게 변환할 수 있습니다. 이를 달성하는 방법을 단계별로 살펴보겠습니다!

## 전제조건

시작하기 전에 몇 가지 사항이 준비되어 있어야 합니다.

-  .NET용 Aspose.Words: .NET용 Aspose.Words가 설치되어 있는지 확인하세요. 당신은 할 수 있습니다[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 AC# 개발 환경.
- 샘플 문서: 작업할 Word 문서입니다. 이 튜토리얼에서는 모든 .docx 파일을 사용할 수 있습니다.
- 기본 C# 지식: C# 프로그래밍에 익숙합니다.

준비가 완료되면 시작해 보세요!

## 네임스페이스 가져오기

.NET용 Aspose.Words를 사용하려면 코드 시작 부분에서 필요한 네임스페이스를 가져와야 합니다. 이렇게 하면 문서 조작에 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: 문서 로드

먼저 변환하려는 Word 문서를 로드해야 합니다. 문서 이름이 다음과 같다고 가정해 보겠습니다.`Rendering.docx` 자리 표시자로 지정된 디렉터리에 위치합니다.`YOUR DOCUMENT DIRECTORY`.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 이 코드는 문서 경로를 초기화하고 Aspose.Words에 로드합니다.`Document` 물체.

## 2단계: ImageSaveOptions 설정

 다음으로`ImageSaveOptions` JPEG 생성 방법을 지정합니다. 여기에는 페이지 범위, 이미지 밝기, 대비 및 해상도 설정이 포함됩니다.

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options.PageSet = new PageSet(0); // 첫 번째 페이지만 변환
options.ImageBrightness = 0.3f;   // 밝기 설정
options.ImageContrast = 0.7f;     // 대비 설정
options.HorizontalResolution = 72f; // 해상도 설정
```

## 3단계: 문서를 JPEG로 저장

마지막으로 정의한 설정을 사용하여 문서를 JPEG 파일로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 이 코드는 첫 번째 페이지를 저장합니다.`Rendering.docx` 지정된 밝기, 대비 및 해상도 설정을 가진 JPEG 이미지로.

## 결론

그리고 거기에 있습니다! Aspose.Words for .NET을 사용하여 사용자 정의된 설정을 사용하여 Word 문서의 특정 페이지를 JPEG 이미지로 성공적으로 변환했습니다. 이 프로세스는 웹 사이트용 이미지 준비, 문서 미리 보기 생성 등 다양한 요구 사항에 맞게 맞춤화될 수 있습니다.

## FAQ

### 여러 페이지를 한 번에 변환할 수 있나요?
 예, 다음을 사용하여 페이지 범위를 지정할 수 있습니다.`PageSet` 재산`ImageSaveOptions`.

### 이미지 품질을 어떻게 조정하나요?
 다음을 사용하여 JPEG 품질을 조정할 수 있습니다.`JpegQuality` 재산`ImageSaveOptions`.

### 다른 이미지 형식으로 저장할 수 있나요?
 예, Aspose.Words는 PNG, BMP, TIFF와 같은 다양한 이미지 형식을 지원합니다. 변경`SaveFormat` ~에`ImageSaveOptions` 따라서.

### 이미지를 저장하기 전에 미리 볼 수 있는 방법이 있나요?
Aspose.Words는 내장된 미리보기 기능을 제공하지 않으므로 미리보기 메커니즘을 별도로 구현해야 합니다.

### Aspose.Words에 대한 임시 라이선스는 어떻게 얻나요?
 다음을 요청할 수 있습니다.[임시 면허증은 여기](https://purchase.aspose.com/temporary-license/).