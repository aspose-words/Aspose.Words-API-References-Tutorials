---
title: 내장된 Arial 및 Times Roman 글꼴 건너뛰기로 PDF 크기 최적화
linktitle: 내장된 Arial 및 Times Roman 글꼴 건너뛰기로 PDF 크기 최적화
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Arial 및 Times Roman 글꼴을 포함하지 않고 최적화된 PDF를 생성하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

이 문서에서는 .NET용 Aspose.Words를 사용하여 포함된 Arial 및 Times Roman 글꼴을 메타파일 크기로 건너뛰어 PDF 크기를 최적화하는 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 문서에 글꼴 포함 모드 옵션을 구성하고 Arial 및 Times Roman 글꼴을 포함하지 않고 PDF를 생성하는 방법을 이해할 수 있습니다.

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

## 3단계: 글꼴 포함을 사용하여 PDF로 저장 옵션 구성

 생성된 PDF에 Arial 및 Times Roman 글꼴 포함을 건너뛰려면`PdfSaveOptions` 객체를 설정하고`FontEmbeddingMode`재산`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## 4단계: 포함된 글꼴 없이 문서를 PDF로 저장

마지막으로 이전에 구성한 저장 옵션을 사용하여 문서를 PDF 형식으로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

그게 다야 ! .NET용 Aspose.Words를 사용하여 Arial 및 Times Roman 글꼴을 포함하지 않고 PDF를 성공적으로 생성했습니다.

### .NET용 Aspose.Words를 사용하여 메타파일 크기에 포함된 Arial 및 Times Roman 글꼴을 건너뛰는 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF 문서에 Arial 및 Times Roman 글꼴 포함을 비활성화하는 방법을 설명했습니다. 설명된 단계를 따르면 이러한 특정 글꼴을 포함하지 않고 PDF 파일을 생성할 수 있습니다. 이를 통해 파일 크기를 줄이고 다양한 플랫폼에서 더 나은 문서 호환성을 보장할 수 있습니다. 이 기능을 사용할 때 글꼴 포함을 비활성화하면 결과를 고려해야 합니다. PDF 파일 생성을 최적화하려면 Aspose.Words for .NET의 더 많은 기능을 자유롭게 탐색해 보세요.

### 자주 묻는 질문

#### 질문: PDF 문서에 Arial 및 Times Roman 글꼴 포함을 비활성화하는 것은 무엇이며 왜 중요한가요?
A: PDF 문서에 Arial 및 Times Roman 글꼴 포함을 비활성화하는 것은 생성된 PDF 파일에 이러한 글꼴을 포함하지 않는 프로세스입니다. PDF 리더 시스템에서 이미 일반적으로 사용되는 글꼴을 포함하지 않음으로써 PDF 파일의 크기를 줄이는 것이 중요할 수 있습니다. 또한 다양한 장치와 플랫폼에서 PDF 문서의 더 나은 호환성과 일관된 모양을 보장하는 데 도움이 될 수 있습니다.

#### Q: PDF 문서에 Arial 및 Times Roman 글꼴을 포함하지 않도록 Aspose.Words for .NET을 구성하려면 어떻게 해야 합니까?
A: PDF 문서에 Arial 및 Times Roman 글꼴을 포함하지 않도록 .NET용 Aspose.Words를 구성하려면 다음 단계를 따르세요.

 교체하여 문서가 있는 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로로.

 다음을 사용하여 처리하려는 문서를 로드합니다.`Document` 클래스와 지정된 문서 경로.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 설정하고`FontEmbeddingMode`재산`PdfFontEmbeddingMode.EmbedAll`. 이렇게 하면 생성된 PDF 파일에 Arial 및 Times Roman을 제외한 모든 글꼴이 포함됩니다.

 사용`Save` 의 방법`Document` 이전에 구성한 저장 옵션을 지정하여 문서를 PDF 형식으로 저장하는 개체입니다.

#### 질문: PDF 문서에 Arial 및 Times Roman 글꼴 포함을 비활성화하면 어떤 이점이 있습니까?
A: PDF 문서에 Arial 및 Times Roman 글꼴 포함을 비활성화하면 다음과 같은 이점이 있습니다.

PDF 파일 크기 감소: Arial 및 Times Roman과 같이 일반적으로 사용 가능한 글꼴을 포함하지 않음으로써 PDF 파일 크기를 줄일 수 있으므로 파일 저장, 공유 및 전송이 더 쉬워집니다.

더 나은 호환성: PDF 리더 시스템에서 일반적으로 사용 가능한 글꼴을 사용하면 다양한 장치 및 플랫폼에서 문서의 더 나은 호환성과 모양을 보장할 수 있습니다.

#### 질문: PDF 문서에 Arial 및 Times Roman 글꼴 포함을 비활성화하면 어떤 결과가 발생합니까?
A: PDF 문서에 Arial 및 Times Roman 글꼴 포함을 비활성화하면 다음과 같은 결과가 나타납니다.

다른 모양: PDF가 열려 있는 시스템에서 Arial 및 Times Roman 글꼴을 사용할 수 없는 경우 대체 글꼴이 사용되며 이로 인해 의도한 것과 다른 모양이 나타날 수 있습니다.

가독성 문제: 사용된 대체 글꼴은 원본 글꼴만큼 읽기 어려울 수 있으며, 이는 문서의 가독성에 영향을 미칠 수 있습니다.