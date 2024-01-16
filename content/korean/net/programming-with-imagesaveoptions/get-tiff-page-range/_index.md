---
title: Tiff 페이지 범위 가져오기
linktitle: Tiff 페이지 범위 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 다양한 TIFF 페이지를 추출하는 방법을 알아보세요. 사용자 정의 TIFF 파일에 대한 전체 튜토리얼입니다.
type: docs
weight: 10
url: /ko/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

이 튜토리얼에서는 제공된 C# 소스 코드를 탐색하여 .NET용 Aspose.Words를 사용하여 다양한 TIFF 페이지를 가져옵니다. 이 기능을 사용하면 문서에서 특정 페이지 범위를 추출하여 TIFF 파일로 저장할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 문서 로드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 이 단계에서는 다음을 사용하여 문서를 로드합니다.`Document` 메서드를 사용하고 로드할 DOCX 파일의 경로를 전달합니다.

## 3단계: 전체 문서를 TIFF로 저장

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

이 단계에서는 다음을 사용하여 전체 문서를 TIFF 형식으로 저장합니다.`Save` 메서드를 사용하고 확장자를 사용하여 출력 파일의 경로를 지정합니다.`.tiff`.

## 4단계: 페이지 범위에 대한 백업 옵션 구성

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 이 단계에서는 특정 페이지 범위에 대한 백업 옵션을 구성합니다. 우리는 새로운 것을 만듭니다`ImageSaveOptions` 원하는 저장 형식을 지정하는 개체입니다. 여기서 TIFF 형식은 "Tiff"입니다. 우리는 사용`PageSet` 추출하려는 페이지 범위를 지정하려면 여기서는 0페이지부터 1페이지(포함)까지입니다. 또한 TIFF 압축을 다음으로 설정했습니다.`Ccitt4` 해상도는 160dpi입니다.

## 5단계: 페이지 범위를 TIFF에 저장

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 이 마지막 단계에서는 지정된 페이지 범위를 다음을 사용하여 TIFF 형식으로 저장합니다.`Save` 메서드를 사용하여 출력 파일의 경로를 전달합니다.`.tiff` 확장명과 지정된 저장 옵션이 함께 제공됩니다.

이제 소스 코드를 실행하여 문서에서 특정 페이지 범위를 가져와 TIFF 파일로 저장할 수 있습니다. 결과 파일은 전체 문서의 경우 "WorkingWithImageSaveOptions.MultipageTiff.tiff"라는 이름으로, 지정된 페이지 범위의 경우 "WorkingWithImageSaveOptions.GetTiffPageRange.tiff"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용하여 Tiff 페이지 범위 가져오기의 샘플 소스 코드

```csharp 

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 다양한 TIFF 페이지를 가져오는 기능을 살펴보았습니다. 문서에서 특정 페이지 범위를 추출하여 TIFF 파일로 저장하는 방법을 배웠습니다.

이 기능은 문서에서 특정 페이지만 추출하여 TIFF와 같은 표준 이미지 형식으로 저장하려는 경우에 유용합니다. 최고 품질의 TIFF 파일을 얻기 위해 압축 및 해상도 옵션을 사용자 정의할 수도 있습니다.

Aspose.Words for .NET은 문서 조작 및 생성을 위한 광범위한 고급 기능을 제공합니다. TIFF 페이지 범위를 얻는 것은 귀하가 원하는 대로 사용할 수 있는 많은 강력한 도구 중 하나입니다.

이 기능을 .NET용 Aspose.Words 프로젝트에 자유롭게 통합하여 문서에서 특정 페이지 범위를 TIFF 형식으로 추출하고 저장할 수 있습니다.