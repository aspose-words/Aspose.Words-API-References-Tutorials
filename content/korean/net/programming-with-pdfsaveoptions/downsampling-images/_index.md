---
title: 이미지 다운샘플링으로 PDF 문서 크기 줄이기
linktitle: 이미지 다운샘플링으로 PDF 문서 크기 줄이기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 이미지를 다운샘플링하여 PDF 문서 크기를 줄입니다. 더 빠른 업로드 및 다운로드 시간을 위해 PDF를 최적화하세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/downsampling-images/
---
## 소개

PDF는 문서 공유부터 eBook 제작에 이르기까지 모든 작업에 사용되는 디지털 세계의 필수 요소입니다. 그러나 특히 이미지가 많은 콘텐츠를 처리할 때 크기가 장애물이 될 수 있습니다. 여기서 다운샘플링 이미지가 작동합니다. PDF 내의 이미지 해상도를 줄이면 품질을 크게 저하시키지 않으면서 파일 크기를 크게 줄일 수 있습니다. 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 이를 달성하는 단계를 안내합니다.

## 전제 조건

코드를 시작하기 전에 필요한 모든 것이 있는지 확인하겠습니다.

1.  .NET용 Aspose.Words: Aspose.Words 라이브러리가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio와 같은 모든 .NET 개발 환경.
3. C# 기본 지식: C# 프로그래밍의 기본을 이해하면 도움이 됩니다.
4.  샘플 문서: Word 문서(예:`Rendering.docx`) PDF로 변환할 이미지가 포함되어 있습니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 코드 파일 상단에 다음을 추가하세요.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

이제 프로세스를 관리 가능한 단계로 나누어 보겠습니다.

## 1단계: 문서 로드

첫 번째 단계는 Word 문서를 로드하는 것입니다. 여기에서 문서 디렉터리의 경로를 지정합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

이 단계에서는 지정된 디렉터리에서 Word 문서를 로드합니다. 꼭 교체하세요`"YOUR DOCUMENT DIRECTORY"`문서가 있는 실제 경로를 사용합니다.

## 2단계: 다운샘플링 옵션 구성

다음으로 다운샘플링 옵션을 구성해야 합니다. 여기에는 이미지의 해상도와 해상도 임계값 설정이 포함됩니다.

```csharp
// 다운샘플링을 위한 최소 임계값을 설정할 수 있습니다.
// 이 값은 입력 문서의 두 번째 이미지가 다운샘플링되는 것을 방지합니다.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 여기서는 새로운 인스턴스를 생성합니다.`PdfSaveOptions` 그리고 설정`Resolution` 36DPI로,`ResolutionThreshold` 128DPI로. 즉, 해상도가 128DPI보다 높은 모든 이미지는 36DPI로 다운샘플링됩니다.

## 3단계: 문서를 PDF로 저장

마지막으로 구성된 옵션을 사용하여 문서를 PDF로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

이 마지막 단계에서는 지정된 다운샘플링 옵션을 사용하여 문서를 동일한 디렉터리에 PDF로 저장합니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 이미지를 다운샘플링하여 PDF 크기를 성공적으로 줄였습니다. 이렇게 하면 PDF를 더욱 쉽게 관리할 수 있을 뿐만 아니라 업로드, 다운로드 속도가 빨라지고 보기 환경이 더욱 원활해집니다.

## FAQ

### 다운샘플링이란 무엇입니까?
다운샘플링은 이미지의 해상도를 줄이는 프로세스로, 해당 이미지가 포함된 문서의 파일 크기를 줄이는 데 도움이 됩니다.

### 다운샘플링이 이미지 품질에 영향을 미치나요?
예, 다운샘플링을 하면 이미지 품질이 저하됩니다. 그러나 그 영향은 해상도 감소 정도에 따라 달라집니다. 이는 파일 크기와 이미지 품질 간의 균형입니다.

### 다운샘플링할 이미지를 선택할 수 있나요?
 예, 설정을 통해`ResolutionThreshold`를 사용하면 원본 해상도에 따라 다운샘플링할 이미지를 제어할 수 있습니다.

### 다운샘플링에 이상적인 해상도는 무엇입니까?
이상적인 해상도는 특정 요구 사항에 따라 다릅니다. 일반적으로 웹 이미지에는 72DPI가 사용되는 반면 인쇄 품질에는 더 높은 해상도가 사용됩니다.

### .NET용 Aspose.Words는 무료인가요?
 Aspose.Words for .NET은 상용 제품이지만 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/) 또는[임시 면허증](https://purchase.aspose.com/temporary-license/).