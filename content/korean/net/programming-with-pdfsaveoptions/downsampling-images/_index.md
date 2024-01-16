---
title: 이미지 다운샘플링으로 PDF 문서 크기 줄이기
linktitle: 이미지 다운샘플링으로 PDF 문서 크기 줄이기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 이미지를 다운샘플링하여 PDF 문서 크기를 줄이는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/downsampling-images/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 이미지를 다운샘플링하여 PDF 문서 크기를 줄이는 단계를 안내합니다. 이렇게 하면 생성된 PDF 파일의 크기가 줄어듭니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드

PDF로 변환하려는 문서를 업로드하여 시작하십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

문서의 올바른 경로를 지정해야 합니다.

## 2단계: PDF 저장 옵션 구성

PdfSaveOptions 클래스의 인스턴스를 만들고 이미지 축소 옵션을 설정합니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 그만큼`Resolution` 속성은 이미지의 목표 해상도를 지정하고`ResolutionThreshold`속성은 이미지가 축소되지 않는 최소 해상도를 지정합니다.

## 3단계: 문서를 PDF로 변환

 사용`Save` 저장 옵션을 지정하여 문서를 PDF로 변환하는 방법:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

변환된 PDF를 저장할 올바른 경로를 지정했는지 확인하세요.

### .NET용 Aspose.Words를 사용하여 이미지 다운샘플링을 위한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// 다운샘플링을 위한 최소 임계값을 설정할 수 있습니다.
	// 이 값은 입력 문서의 두 번째 이미지가 다운샘플링되는 것을 방지합니다.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

다음 단계를 따르면 Aspose.Words for .NET을 사용하여 PDF로 변환할 때 이미지 해상도를 쉽게 줄일 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF로 변환할 때 이미지 샘플링을 사용하여 PDF 문서의 크기를 줄이는 방법을 설명했습니다. 설명된 단계를 따르면 이미지의 해상도와 생성된 PDF 파일의 크기를 쉽게 줄일 수 있습니다. 문서의 올바른 경로를 지정하고 필요에 따라 이미지 샘플링 옵션을 구성하십시오. PDF 파일 크기를 줄이면 다양한 플랫폼에서 파일을 더 쉽게 공유하고, 저장하고, 빠르게 로드할 수 있습니다. Aspose.Words for .NET을 사용하여 이미지 샘플링을 통해 PDF 문서 크기를 줄이는 이점을 누려보세요.

### 자주 묻는 질문

#### Q: 이미지 샘플링으로 PDF 문서의 크기를 줄이는 것은 무엇입니까?
A: 이미지 샘플링으로 PDF 문서 크기를 줄이는 것은 PDF로 변환할 때 이미지의 해상도를 줄여 생성된 PDF 파일의 크기를 줄이는 것입니다. 이를 통해 저장 공간 사용이 최적화되고 PDF 파일을 더 쉽게 공유하고 전송할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 이미지 샘플링으로 PDF 문서 크기를 어떻게 줄일 수 있나요?
A: .NET용 Aspose.Words를 사용하여 이미지 샘플링으로 PDF 문서 크기를 줄이려면 다음 단계를 따르세요.

 교체하여 문서가 있는 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENTS DIRECTORY"` 문서 디렉토리의 실제 경로로.

 PDF로 변환하려는 문서를 로드합니다.`Document` 클래스를 지정하고 지정된 문서 디렉터리에 있는 문서의 경로를 지정합니다.

 인스턴스를 생성하여 PDF로 저장 옵션을 구성합니다.`PdfSaveOptions` 클래스를 사용하여 이미지 샘플링 옵션을 설정합니다.`DownsampleOptions` 재산. 다음을 사용하여 이미지의 대상 해상도를 지정할 수 있습니다.`Resolution` 속성을 사용하여 이미지가 축소되지 않는 최소 해상도 임계값을 설정합니다.`ResolutionThreshold` 재산.

 다음을 사용하여 문서를 PDF 형식으로 저장합니다.`Save` 의 방법`Document` 경로와 저장 옵션을 지정하는 클래스입니다.

#### Q: 이미지 샘플링을 통해 PDF 문서 크기를 줄이면 어떤 이점이 있습니까?
A: 이미지 샘플링을 통해 PDF 문서 크기를 줄이면 다음과 같은 이점이 있습니다.

PDF 파일 크기 감소: 이미지 샘플링은 PDF 문서의 이미지 해상도를 줄여서 PDF 파일 크기를 크게 줄입니다. 이를 통해 특히 이메일이나 온라인을 통해 파일을 쉽게 공유하고 전송할 수 있습니다.

저장 공간 최적화: PDF 파일의 크기를 줄이면 특히 고해상도 이미지가 포함된 PDF 파일이 많은 경우 저장 공간 사용을 최적화하는 데 도움이 됩니다.

성능 개선: 작은 PDF 파일은 더 빠르게 로드되며 다른 장치에서 더 빠르게 열고 볼 수 있습니다.