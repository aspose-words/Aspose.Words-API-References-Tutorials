---
title: 변환된 요소 래스터화
linktitle: 변환된 요소 래스터화
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PCL 형식으로 변환할 때 변환된 요소의 래스터화를 비활성화하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET은 C# 애플리케이션에서 Word 문서를 생성, 조작 및 변환하기 위한 강력한 라이브러리입니다. Aspose.Words가 제공하는 기능 중에는 문서를 다른 형식으로 변환할 때 변환된 요소를 래스터화하는 기능이 있습니다. 이 가이드에서는 문서를 PCL 형식으로 변환할 때 변환된 요소의 래스터화를 비활성화하기 위해 .NET용 Aspose.Words의 C# 소스 코드를 사용하는 방법을 보여줍니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 Word 문서로 Words 처리를 쉽고 효율적으로 만들어주는 인기 있는 라이브러리입니다. 변환 중 변환된 요소 래스터화 지원을 포함하여 Word 문서 생성, 편집 및 변환을 위한 다양한 기능을 제공합니다.

## Word 문서 로드

첫 번째 단계는 PCL 형식으로 변환하려는 Word 문서를 로드하는 것입니다. Document 클래스를 사용하여 소스 파일에서 문서를 로드합니다. 예는 다음과 같습니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

이 예에서는 문서 디렉터리에 있는 "Rendering.docx" 문서를 로드합니다.

## 백업 옵션 구성

다음 단계는 PCL 형식으로 변환하기 위한 저장 옵션을 구성하는 것입니다. PclSaveOptions 클래스를 사용하고 RasterizeTransformedElements 속성을 false로 설정합니다. 수행 방법은 다음과 같습니다.

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

새 PclSaveOptions 개체를 만들고 SaveFormat 속성을 SaveFormat.Pcl로 설정하여 문서를 PCL 형식으로 저장하도록 지정합니다. 다음으로 RasterizeTransformedElements 속성을 false로 설정하여 변환된 요소의 래스터화를 비활성화합니다.

## 문서를 PCL 형식으로 변환

이제 저장 옵션을 구성했으므로 문서를 PCL 형식으로 변환할 수 있습니다. 저장 옵션을 지정하여 변환된 문서를 PCL 형식으로 저장하려면 Document 클래스의 Save 메서드를 사용합니다. 예는 다음과 같습니다.

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

이 예에서는 지정된 저장 옵션을 사용하여 변환된 문서를 "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl"로 저장합니다.

### .NET용 Aspose.Words를 사용한 "변환된 요소 래스터화" 기능의 소스 코드 예

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word 문서 로드


Document doc = new Document(dataDir + "Rendering.docx");

// PCL 형식으로 변환하기 위한 백업 옵션 구성
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// 문서를 PCL 형식으로 변환
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## 결론

이 가이드에서는 제공된 C# 소스 코드를 사용하여 문서를 PCL 형식으로 변환할 때 변환된 요소의 래스터화를 비활성화하기 위해 Aspose.Words for .NET을 사용하는 방법을 다루었습니다. 제공된 단계를 따르면 Word 문서를 다른 형식으로 변환할 때 변환된 요소의 래스터화 동작을 쉽게 제어할 수 있습니다. Aspose.Words는 변환된 요소를 사용하여 작업할 수 있는 엄청난 유연성과 기능을 제공하므로 특정 요구 사항에 맞게 변환된 문서를 정확하게 만들 수 있습니다.