---
title: 핵심 글꼴을 포함하지 않음으로써 PDF 파일 크기 줄이기
linktitle: 핵심 글꼴을 포함하지 않음으로써 PDF 파일 크기 줄이기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 PDF로 변환할 때 핵심 글꼴을 포함하지 않음으로써 PDF 파일 크기를 줄이는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

이 튜토리얼에서는 .NET용 Aspose.Words에 핵심 글꼴을 포함하지 않음으로써 PDF 파일 크기를 줄이는 방법을 단계별로 안내합니다. 이 기능을 사용하면 Word 문서를 변환할 때 Arial, Times New Roman 등과 같은 기본 글꼴을 PDF에 포함해야 하는지 여부를 제어할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드

PDF로 변환하려는 Word 문서를 업로드하여 시작하십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Word 문서의 올바른 경로를 지정해야 합니다.

## 2단계: PDF 변환 옵션 설정

PdfSaveOptions 클래스의 인스턴스를 만들고 기본 글꼴 포함 방지를 활성화합니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

이 옵션은 기본 글꼴을 PDF에 포함할지 여부를 제어합니다.

## 3단계: 문서를 PDF로 변환

 사용`Save` 변환 옵션을 지정하여 Word 문서를 PDF로 변환하는 방법:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

변환된 PDF를 저장할 올바른 경로를 지정했는지 확인하세요.

### .NET용 Aspose.Words를 사용하여 핵심 글꼴 포함 방지에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words에 핵심 글꼴 포함을 방지하는 기능을 사용하는 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// 출력 PDF에는 Arial, Times New Roman 등과 같은 핵심 글꼴이 포함되지 않습니다.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 Word 문서를 변환할 때 기본 글꼴을 PDF에 포함할지 여부를 쉽게 제어할 수 있습니다.


## 결론

이 튜토리얼에서는 Aspose.Words for .NET에 기본 글꼴을 포함하지 않고 PDF 파일의 크기를 줄이는 방법을 설명했습니다. 이 기능을 사용하면 Word 문서를 변환할 때 기본 글꼴을 PDF에 포함할지 여부를 제어할 수 있습니다. 설명된 단계를 따르면 기본 글꼴의 포함 또는 비포함을 쉽게 제어할 수 있으며, 이를 통해 PDF 파일 크기를 줄이고 다양한 장치 및 플랫폼에서 문서의 호환성과 일관된 모양을 보장할 수 있습니다. 기본 글꼴을 포함하지 않은 결과를 고려하고 문서가 예상대로 렌더링되는지 실험하는 것을 잊지 마십시오.

### 자주 묻는 질문

#### Q: PDF 파일에 기본 글꼴을 포함하지 않는 옵션은 무엇이며 이것이 중요한 이유는 무엇입니까?
답변: PDF 파일에 기본 글꼴을 포함하지 않는 옵션은 Word 문서를 변환할 때 Arial, Times New Roman 등과 같은 기본 글꼴을 PDF에 포함해야 하는지 여부를 제어합니다. 이는 PDF 리더 시스템에서 일반적으로 사용할 수 있는 글꼴을 포함하지 않음으로써 PDF 파일의 크기를 줄이는 데 중요할 수 있습니다. 또한 다양한 장치와 플랫폼에서 PDF 문서의 더 나은 호환성과 일관된 모양을 보장하는 데 도움이 될 수 있습니다.

#### Q: PDF 파일에 기본 글꼴을 포함하지 않도록 Aspose.Words for .NET을 어떻게 구성합니까?
A: PDF 파일에 핵심 글꼴을 포함하지 않도록 .NET용 Aspose.Words를 구성하려면 다음 단계를 따르세요.

 교체하여 문서가 있는 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENTS DIRECTORY"` 문서 디렉토리의 실제 경로로.

 다음을 사용하여 PDF로 변환하려는 Word 문서를 로드합니다.`Document` 클래스와 지정된 문서 경로.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 설정하고`UseCoreFonts`재산`true`. 이렇게 하면 생성된 PDF 파일에 기본 글꼴이 포함되는 것을 방지할 수 있습니다.

 사용`Save` 의 방법`Document` 이전에 구성한 변환 옵션을 지정하여 문서를 PDF 형식으로 저장하는 개체입니다.

#### Q: PDF 파일에 기본 글꼴을 포함하지 않으면 어떤 이점이 있습니까?
A: PDF 파일에 기본 글꼴을 포함하지 않으면 다음과 같은 이점이 있습니다.

PDF 파일 크기 감소: Arial, Times New Roman 등과 같이 일반적으로 사용 가능한 글꼴을 포함하지 않음으로써 PDF 파일 크기를 줄일 수 있으므로 파일 저장, 공유 및 전송이 더 쉬워집니다.

더 나은 호환성: PDF 리더 시스템에서 일반적으로 사용 가능한 기본 글꼴을 사용하면 다양한 장치 및 플랫폼에서 더 나은 호환성과 문서 모양을 보장할 수 있습니다.

#### Q: PDF 파일에 기본 글꼴을 포함하지 않으면 어떤 결과가 발생합니까?
A: PDF 파일에 기본 글꼴을 포함하지 않은 결과는 다음과 같습니다.

다른 모양: PDF가 열려 있는 시스템에서 기본 글꼴을 사용할 수 없는 경우 대체 글꼴이 사용되며 이로 인해 의도한 것과 다른 모양이 나타날 수 있습니다.

가독성 문제: 사용된 대체 글꼴은 원본 글꼴만큼 읽기 쉽지 않을 수 있으며, 이는 문서의 가독성에 영향을 미칠 수 있습니다.