---
title: 포함된 글꼴을 비활성화하여 PDF 크기 줄이기
linktitle: 포함된 글꼴을 비활성화하여 PDF 크기 줄이기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 PDF로 변환할 때 Windows 글꼴 포함을 비활성화하고 PDF 크기를 줄이는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 PDF 문서에 Windows 글꼴 포함을 비활성화하여 PDF 크기를 줄이는 단계를 안내합니다. 글꼴 포함을 비활성화하면 생성된 PDF 파일의 크기를 줄일 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드

PDF로 변환하려는 문서를 업로드하여 시작하십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

문서의 올바른 경로를 지정해야 합니다.

## 2단계: PDF 저장 옵션 설정

PdfSaveOptions 클래스의 인스턴스를 만들고 글꼴을 포함하는 방법을 지정합니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

이 옵션을 사용하면 생성된 PDF 파일에서 Windows 글꼴 통합을 비활성화할 수 있습니다.

## 3단계: 문서를 PDF로 변환

 사용`Save` 변환 옵션을 지정하여 문서를 PDF로 변환하는 방법:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

변환된 PDF를 저장할 올바른 경로를 지정했는지 확인하세요.

### .NET용 Aspose.Words를 사용하여 Windows 글꼴 포함 비활성화에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 PDF 문서에 Windows 글꼴 포함을 비활성화하는 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// 출력 PDF는 표준 Windows 글꼴을 포함하지 않고 저장됩니다.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 PDF 문서에 Windows 글꼴 포함을 쉽게 비활성화할 수 있습니다.


## 결론

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Windows 글꼴 포함을 비활성화하여 PDF 파일의 크기를 줄이는 방법을 배웠습니다. 글꼴 포함을 비활성화하면 생성된 PDF 파일의 크기를 줄여 파일을 더 쉽게 저장, 공유 및 전송할 수 있습니다. 그러나 Windows 글꼴 포함을 비활성화하면 최종 PDF 문서의 모양과 서식이 변경될 수 있다는 점에 유의하는 것이 중요합니다. 이 기능을 사용할 때 이러한 결과를 고려해야 합니다. PDF 파일 생성을 최적화하려면 Aspose.Words for .NET의 더 많은 기능을 자유롭게 탐색해 보세요.

### 자주 묻는 질문

#### Q: PDF 문서에 Windows 글꼴 포함을 비활성화하는 것은 무엇이며 왜 중요한가요?
답변: PDF 문서에 Windows 글꼴 포함을 비활성화하는 것은 생성된 PDF 파일에 Windows 글꼴이 포함되지 않도록 하는 프로세스입니다. 이렇게 하면 포함된 Windows 글꼴 데이터가 제거되어 PDF 파일의 크기가 줄어듭니다. 이는 PDF 파일의 크기를 줄이는 데 중요할 수 있으며, 이를 통해 PDF 파일을 더 쉽게 저장하고, 공유하고, 더 빠르게 전송할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 PDF 문서에 Windows 글꼴 포함을 비활성화하려면 어떻게 해야 합니까?
A: .NET용 Aspose.Words를 사용하여 PDF 문서에 Windows 글꼴 포함을 비활성화하려면 다음 단계를 따르세요.

 PDF로 변환하려는 문서를 로드합니다.`Document` 클래스 및 문서 경로.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 설정하고`FontEmbeddingMode`재산`PdfFontEmbeddingMode.EmbedNone`. 이렇게 하면 생성된 PDF 파일에 Windows 글꼴이 포함되지 않습니다.

 사용`Save` 의 방법`Document` 이전에 구성한 변환 옵션을 지정하여 문서를 PDF로 변환하는 개체입니다.

#### Q: PDF 문서에 Windows 글꼴 포함을 비활성화하면 어떤 이점이 있습니까?
A: PDF 문서에 Windows 글꼴 포함을 비활성화하면 다음과 같은 이점이 있습니다.

PDF 파일 크기 감소: Windows 글꼴 포함을 비활성화하면 포함된 Windows 글꼴 데이터가 제거되어 생성된 PDF 파일의 크기가 줄어듭니다.

간편한 저장: PDF 파일이 작을수록 저장, 저장 및 전송이 더 쉽습니다.

더 빠른 공유 및 전송: 더 작은 PDF 파일을 더 빠르게 공유하고 전송할 수 있어 시간과 리소스가 절약됩니다.

#### 질문: PDF 문서에 Windows 글꼴 포함을 비활성화하면 어떤 결과가 발생합니까?
A: PDF 문서에 Windows 글꼴 포함을 비활성화하면 다음과 같은 결과가 발생할 수 있습니다.

모양 및 서식 손실: 문서에 지정된 Windows 글꼴을 PDF가 열려 있는 시스템에서 사용할 수 없는 경우 대체 글꼴이 사용되므로 모양과 서식이 잘못될 수 있습니다. 예상과 모양이 다릅니다.

가독성 문제: 사용된 대체 글꼴이 원본 글꼴만큼 읽기 어려운 경우 PDF 문서의 텍스트 가독성에 영향을 미칠 수 있습니다.