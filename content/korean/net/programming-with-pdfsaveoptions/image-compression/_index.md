---
title: PDF 문서의 이미지 압축
linktitle: PDF 문서의 이미지 압축
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF 문서의 이미지를 압축하는 방법을 알아보세요. 최적화된 파일 크기와 품질을 위해 이 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/image-compression/
---
## 소개

오늘날의 디지털 시대에 문서 크기 관리는 성능과 저장 효율성 모두에 매우 중요합니다. 대규모 보고서를 처리하든 복잡한 프레젠테이션을 처리하든 품질을 저하시키지 않으면서 파일 크기를 줄이는 것이 필수적입니다. PDF 문서의 이미지 압축은 이러한 목표를 달성하기 위한 핵심 기술입니다. .NET용 Aspose.Words를 사용하고 있다면 행운이 따릅니다! 이 튜토리얼은 .NET용 Aspose.Words를 사용하여 PDF 문서의 이미지를 압축하는 과정을 안내합니다. 다양한 압축 옵션과 이를 효과적으로 적용하여 PDF가 품질과 크기 모두에 최적화되도록 하는 방법을 살펴보겠습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET용 Aspose.Words: .NET용 Aspose.Words가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/words/net/).

2. C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 이 자습서에서 제공되는 코드 예제를 이해하는 데 도움이 됩니다.

3. 개발 환경: Visual Studio와 같은 .NET 개발 환경이 설정되어 있는지 확인하세요.

4. 샘플 문서: 이미지 압축 테스트를 위해 샘플 Word 문서(예: "Rendering.docx")를 준비합니다.

5. Aspose 라이선스: Aspose.Words for .NET의 라이선스 버전을 사용하는 경우 라이선스가 올바르게 구성되어 있는지 확인하세요. 임시 라이센스가 필요한 경우 다음에서 얻을 수 있습니다.[Aspose의 임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).

## 네임스페이스 가져오기

.NET용 Aspose.Words를 사용하여 PDF 문서에서 이미지 압축을 시작하려면 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

이러한 네임스페이스는 Word 문서를 조작하고 다양한 옵션을 사용하여 PDF로 저장하는 데 필요한 핵심 기능에 대한 액세스를 제공합니다.

## 1단계: 문서 디렉토리 설정

코딩을 시작하기 전에 문서 디렉토리의 경로를 정의하십시오. 이렇게 하면 파일을 쉽게 찾고 저장할 수 있습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 샘플 문서가 저장된 경로를 사용하세요.

## 2단계: Word 문서 로드

 다음으로 Word 문서를`Aspose.Words.Document` 물체. 이렇게 하면 프로그래밍 방식으로 문서 작업을 수행할 수 있습니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 여기,`"Rendering.docx"` 샘플 Word 문서의 이름입니다. 이 파일이 지정된 디렉토리에 있는지 확인하십시오.

## 3단계: 기본 이미지 압축 구성

 만들기`PdfSaveOptions`이미지 압축을 포함한 PDF 저장 옵션을 구성하는 개체입니다. 설정`ImageCompression`재산`PdfImageCompression.Jpeg` 이미지에 JPEG 압축을 사용하려면

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	// JPEG를 사용하여 이미지 압축
    ImageCompression = PdfImageCompression.Jpeg,
	// 선택 사항: PDF의 양식 필드 유지
    PreserveFormFields = true
};
```

## 4단계: 기본 압축을 사용하여 문서 저장

구성된 이미지 압축 옵션을 사용하여 Word 문서를 PDF로 저장합니다. 이렇게 하면 PDF의 이미지에 JPEG 압축이 적용됩니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

 이 예에서는 출력 PDF의 이름이 지정됩니다.`"WorkingWithPdfSaveOptions.PdfImageCompression.pdf"`. 필요에 따라 파일 이름을 조정합니다.

## 5단계: PDF/A 규격을 준수하는 고급 압축 구성

 더 나은 압축을 위해, 특히 PDF/A 표준을 준수해야 하는 경우 추가 옵션을 구성할 수 있습니다. 설정`Compliance`재산`PdfCompliance.PdfA2u` 그리고 조정`JpegQuality` 재산.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
	// PDF/A-2u에 대한 규격 설정
    Compliance = PdfCompliance.PdfA2u,
	// JPEG 압축 사용
    ImageCompression = PdfImageCompression.Jpeg,
	// JPEG 품질을 조정하여 압축 수준 제어
    JpegQuality = 100 
};
```

## 6단계: 고급 압축을 사용하여 문서 저장

고급 압축 설정을 사용하여 Word 문서를 PDF로 저장합니다. 이 구성을 통해 PDF는 PDF/A 표준을 준수하고 고품질 JPEG 압축을 사용합니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```

 여기서 출력 PDF의 이름은 다음과 같습니다.`"WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf"`. 원하는 대로 파일 이름을 수정합니다.

## 결론

이미지를 압축하여 PDF 문서의 크기를 줄이는 것은 문서 성능과 저장 공간을 최적화하는 데 있어 중요한 단계입니다. .NET용 Aspose.Words를 사용하면 이미지 압축을 효과적으로 제어할 수 있는 강력한 도구를 사용할 수 있습니다. 이 튜토리얼에 설명된 단계를 따르면 PDF 문서의 품질이 높고 컴팩트하다는 것을 확인할 수 있습니다. 기본 압축이 필요하든 고급 압축이 필요하든 Aspose.Words는 요구 사항을 충족하는 유연성을 제공합니다.


## FAQ

### PDF의 이미지 압축이란 무엇입니까?
이미지 압축은 이미지 품질을 저하시켜 PDF 문서의 파일 크기를 줄여 저장 및 성능을 최적화하는 데 도움이 됩니다.

### .NET용 Aspose.Words는 이미지 압축을 어떻게 처리합니까?
.NET용 Aspose.Words는 다음을 제공합니다.`PdfSaveOptions` JPEG 압축을 포함한 다양한 이미지 압축 옵션을 설정할 수 있는 클래스입니다.

### PDF/A 표준을 준수하기 위해 .NET용 Aspose.Words를 사용할 수 있습니까?
예, Aspose.Words는 PDF/A 준수를 지원하므로 보관 및 장기 보존 표준을 충족하는 형식으로 문서를 저장할 수 있습니다.

### PDF 파일 크기에 JPEG 품질이 미치는 영향은 무엇입니까?
JPEG 품질 설정이 높을수록 이미지 품질은 좋아지지만 파일 크기가 커지고, 품질 설정이 낮을수록 파일 크기는 줄어들지만 이미지 선명도에 영향을 줄 수 있습니다.

### .NET용 Aspose.Words에 대한 자세한 정보는 어디서 찾을 수 있나요?
 Aspose.Words for .NET에 대해 더 자세히 알아볼 수 있습니다.[선적 서류 비치](https://reference.aspose.com/words/net/), [지원하다](https://forum.aspose.com/c/words/8) , 그리고[다운로드](https://releases.aspose.com/words/net/) 페이지.

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