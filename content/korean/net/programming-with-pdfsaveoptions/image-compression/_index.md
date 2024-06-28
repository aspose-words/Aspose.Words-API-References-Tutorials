---
title: PDF 문서의 이미지 압축
linktitle: PDF 문서의 이미지 압축
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF 문서의 압축 이미지에 대한 단계별 안내입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/image-compression/
---

이 문서에서는 .NET용 Aspose.Words와 함께 PDF 문서의 이미지 압축 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 문서의 이미지를 압축하는 방법과 적절한 이미지 압축을 사용하여 PDF를 생성하는 방법을 이해할 수 있습니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 문서 디렉터리 정의

 시작하려면 문서가 있는 디렉터리의 경로를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 업로드

다음으로 처리하려는 문서를 로드해야 합니다. 이 예에서는 문서가 "Rendering.docx"이고 지정된 문서 디렉터리에 있다고 가정합니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: 이미지 압축을 사용하여 PDF로 저장 옵션 구성

 PDF로 변환할 때 이미지를 압축하려면 다음을 구성해야 합니다.`PdfSaveOptions` 물체. 필요한 경우 이미지 압축 유형, JPEG 품질 및 기타 PDF 준수 옵션을 설정할 수 있습니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## 4단계: 이미지 압축을 사용하여 문서를 PDF로 저장

마지막으로 이전에 구성한 저장 옵션을 사용하여 문서를 PDF 형식으로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## 5단계: 이미지 압축을 사용하여 PDF/A-2u에 저장하기 위한 옵션 구성

이미지 압축을 사용하여 PDF/A-2u 호환 PDF를 생성하려는 경우 추가 저장 옵션을 구성할 수 있습니다.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // 파일 크기를 줄이려면 품질이 50%인 JPEG 압축을 사용하세요.
};
```

## 6단계: 이미지 압축을 사용하여 문서를 PDF/A-2u로 저장

앞서 구성한 추가 저장 옵션을 사용하여 문서를 PDF/A-2u 형식으로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



그게 다야 ! 문서의 이미지를 성공적으로 압축하고 .NET용 Aspose.Words를 사용하여 적절한 이미지 압축으로 PDF를 생성했습니다.

### .NET용 Aspose.Words를 사용하여 이미지를 압축하기 위한 샘플 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // 파일 크기를 줄이려면 50% 품질의 JPEG 압축을 사용하세요.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF 문서의 이미지를 압축하는 방법을 설명했습니다. 설명된 단계를 따르면 PDF 문서의 이미지 크기를 쉽게 줄이고 적절한 이미지 압축을 사용하여 PDF를 생성할 수 있습니다. .NET용 Aspose.Words의 이미지 압축 기능을 사용하여 이미지 품질을 유지하면서 PDF 문서의 크기를 최적화하세요.

### 자주 묻는 질문

#### Q: PDF 문서의 이미지 압축이란 무엇입니까?
A: PDF 문서의 이미지를 압축하는 것은 PDF 문서에 포함된 이미지의 크기를 줄여 PDF 파일의 전체 크기를 줄이는 것입니다. 이렇게 하면 필요한 저장 공간이 줄어들고 PDF를 로드하고 볼 때 성능이 향상됩니다.

#### Q: Aspose.Words for .NET을 사용하여 PDF 문서의 이미지를 어떻게 압축할 수 있나요?
A: .NET용 Aspose.Words를 사용하여 PDF 문서의 이미지를 압축하려면 다음 단계를 따르세요.

 인스턴스를 생성합니다.`Document` Word 문서의 경로를 지정하는 클래스입니다.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 설정하고`ImageCompression`재산`PdfImageCompression.Jpeg` JPEG 압축을 사용하려면

필요에 따라 JPEG 품질과 같은 다른 이미지 압축 옵션을 설정할 수도 있습니다.

 사용`Save` 의 방법`Document`저장 옵션을 지정하여 문서를 PDF 형식으로 저장하는 클래스입니다.

#### Q: 표준 이미지 압축과 PDF/A-2u 이미지 압축의 차이점은 무엇입니까?
A: 표준 이미지 압축은 양식 필드를 유지하면서 PDF 문서의 이미지 크기를 줄입니다. 이렇게 하면 양식 필드 기능을 손상시키지 않고 PDF 파일의 전체 크기가 줄어듭니다.

PDF/A-2u를 사용한 이미지 압축은 이미지 압축을 적용하면서 PDF/A-2u 표준을 준수하는 PDF 파일을 생성할 수 있는 추가 옵션입니다. PDF/A-2u는 보관용 PDF 문서에 대한 ISO 표준이며 문서의 장기 보존을 보장합니다.
