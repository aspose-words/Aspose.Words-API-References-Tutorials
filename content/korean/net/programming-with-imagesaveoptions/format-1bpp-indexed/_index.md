---
title: 형식 1Bpp 인덱스
linktitle: 형식 1Bpp 인덱스
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 인덱싱된 1bpp로 이미지 형식을 지정하는 방법을 알아보세요. 낮은 색상 심도 이미지에 대한 완전한 튜토리얼입니다.
type: docs
weight: 10
url: /ko/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 "Format 1Bpp Indexed" 기능을 위해 제공된 C# 소스 코드를 살펴보겠습니다. 이 기능을 사용하면 픽셀당 1비트(1bpp)의 색상 깊이와 인덱스 색상 모드를 사용하여 문서의 이미지 형식을 PNG 형식으로 지정할 수 있습니다.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 이 단계에서는 이미지에 대한 백업 옵션을 구성합니다. 우리는 새로운 것을 만듭니다`ImageSaveOptions`원하는 저장 형식을 지정하는 개체입니다. 여기서는 PNG 형식의 경우 "Png"입니다. 또한 이미지에 포함할 페이지, 흑백 색상 모드 및 인덱스된 1bpp 픽셀 형식을 정의합니다.

## 4단계: 이미지 백업하기

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 이 마지막 단계에서는 다음을 사용하여 문서 이미지를 PNG 형식으로 저장합니다.`Save` 메서드를 지정하고 지정된 저장 옵션과 함께 출력 파일에 경로를 전달합니다.

이제 소스 코드를 실행하여 문서 이미지를 1bpp 인덱스 색상 깊이의 PNG 형식으로 형식화할 수 있습니다. 결과 파일은 "WorkingWithImageSaveOptions.Format1BppIndexed.Png"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용하여 인덱싱된 형식 1Bpp의 샘플 소스 코드

```csharp 
 
			 // 문서 디렉터리 경로
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### 결론

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 1Bpp 인덱스 형식 기능을 살펴보았습니다. 픽셀당 1비트(1bpp)의 색상 깊이와 인덱스 색상 모드를 사용하여 문서의 이미지 형식을 PNG 형식으로 지정하는 방법을 배웠습니다.

이 기능은 색상 심도가 낮고 파일 크기가 작은 이미지를 얻으려는 경우에 유용합니다. 1Bpp 인덱스 형식을 사용하면 인덱스 색상 팔레트를 사용하여 이미지를 표현할 수 있으며 이는 일부 특정 응용 프로그램에 유용할 수 있습니다.

Aspose.Words for .NET은 문서 조작 및 생성을 위한 광범위한 고급 기능을 제공합니다. 1Bpp 인덱스 형식은 원하는대로 사용할 수 있는 많은 강력한 도구 중 하나입니다.