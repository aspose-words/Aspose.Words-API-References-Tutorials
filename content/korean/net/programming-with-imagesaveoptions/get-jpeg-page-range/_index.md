---
title: JPEG 페이지 범위 가져오기
linktitle: JPEG 페이지 범위 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 다양한 JPEG 페이지를 얻는 방법을 알아보세요. 사용자 정의 이미지 추출을 위한 완전한 튜토리얼입니다.
type: docs
weight: 10
url: /ko/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 "JPEG 페이지 범위 가져오기" 기능에 제공된 C# 소스 코드를 살펴보겠습니다. 이 기능을 사용하면 문서의 특정 페이지 범위를 JPEG 형식의 이미지로 변환할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 문서 로드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 이 단계에서는 다음을 사용하여 문서를 로드합니다.`Document` 메서드를 사용하고 로드할 DOCX 파일의 경로를 전달합니다.

## 3단계: 이미지 백업 옵션 구성

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 이 단계에서는 이미지에 대한 백업 옵션을 구성합니다. 우리는 새로운 것을 만듭니다`ImageSaveOptions` 원하는 저장 형식을 지정하는 객체입니다. 여기서 JPEG 형식은 "Jpeg"입니다. 또한 다음을 사용하여 변환할 페이지 범위를 설정했습니다.`PageSet`물체. 마지막으로 이미지의 밝기와 대비를 조정합니다.`ImageBrightness`그리고`ImageContrast` 각각 속성. 또한 다음을 사용하여 수평 해상도를 변경합니다.`HorizontalResolution` 재산.

## 4단계: 이미지 백업하기

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 이 마지막 단계에서는 지정된 페이지 범위의 이미지를 다음을 사용하여 JPEG 형식으로 저장합니다.`Save` 메서드를 지정하고 지정된 저장 옵션과 함께 출력 파일에 경로를 전달합니다.

이제 소스 코드를 실행하여 문서의 특정 페이지 범위를 JPEG 이미지로 변환할 수 있습니다. 결과 파일은 "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용하여 Jpeg 페이지 범위 가져오기의 샘플 소스 코드

```csharp 
 // 문서 디렉터리 경로
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// 문서의 첫 번째 페이지만 변환하려면 "PageSet"을 "0"으로 설정합니다.
options.PageSet = new PageSet(0);

// 이미지의 밝기와 대비를 변경합니다.
// 둘 다 0-1 척도이며 기본적으로 0.5입니다.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// 수평 해상도를 변경합니다.
// 이러한 속성의 기본값은 96dpi 해상도의 경우 96.0입니다.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 JPEG 페이지 범위를 가져오는 기능을 살펴보았습니다. 저장 옵션을 사용자 정의하면서 문서의 특정 페이지 범위를 JPEG 형식의 이미지로 변환하는 방법을 배웠습니다.

이 기능은 문서의 특정 페이지를 추출하여 JPEG 이미지로 저장하려는 경우에 유용합니다. 또한 이미지의 밝기, 대비 및 수평 해상도를 조정하여 개인화된 결과를 얻을 수도 있습니다.

Aspose.Words for .NET은 문서 조작 및 생성을 위한 광범위한 고급 기능을 제공합니다. JPEG 페이지 범위를 얻는 것은 귀하가 원하는 대로 사용할 수 있는 많은 강력한 도구 중 하나입니다.

이 기능을 .NET용 Aspose.Words 프로젝트에 자유롭게 통합하여 문서에서 고품질 JPEG 이미지를 얻으세요.