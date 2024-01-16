---
title: PDF 문서에 하위 집합 글꼴 포함
linktitle: PDF 문서에 하위 집합 글꼴 포함
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF 문서에 글꼴 하위 집합을 포함하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

이 문서에서는 .NET용 Aspose.Words와 함께 글꼴 하위 집합 포함 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼을 마치면 문서에 글꼴 하위 집합을 포함하고 문서에 사용된 글리프만 포함된 PDF를 생성하는 방법을 이해할 수 있습니다.

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

## 3단계: PDF로 저장 옵션 구성

 문서에 사용된 글꼴의 하위 집합만 포함하는 PDF를 만들려면 다음을 구성해야 합니다.`PdfSaveOptions` 이의를 제기하다`EmbedFullFonts` 다음으로 설정된 속성`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## 4단계: 글꼴 하위 집합을 사용하여 문서를 PDF로 저장

 마지막으로 글꼴 하위 집합을 사용하여 문서를 PDF로 저장할 수 있습니다. 출력 파일 이름과`saveOptions` 이전 단계에서 구성한 개체입니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

그게 다야 ! 문서에 글꼴 하위 집합을 성공적으로 포함하고 .NET용 Aspose.Words를 사용하여 문서에 사용된 글리프만 포함된 PDF를 생성했습니다.

### .NET용 Aspose.Words에 글꼴 하위 집합을 포함하기 위한 샘플 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// 출력 PDF에는 문서에 있는 글꼴의 하위 집합이 포함됩니다.
	// 문서에 사용된 글리프만 PDF 글꼴에 포함됩니다.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF 문서에 글꼴 하위 집합을 포함하는 방법을 배웠습니다. 글꼴 하위 집합을 포함하면 실제로 사용된 문자만 사용하여 문서의 모양을 유지하면서 PDF 파일의 크기를 줄이는 데 도움이 됩니다. 이렇게 하면 PDF를 보고 인쇄할 때 더 나은 호환성과 성능이 보장됩니다. .NET용 Aspose.Words의 기능을 더 자세히 탐색하여 포함된 글꼴 하위 집합이 있는 PDF 문서 생성을 최적화하세요.

### 자주 묻는 질문

#### Q: PDF 문서에 글꼴 하위 집합을 포함한다는 것은 무엇입니까?
답변: PDF 문서에 글꼴 하위 집합을 포함시키는 것은 전체 글꼴을 모두 포함하는 것이 아니라 문서에 사용된 글리프만 포함하는 프로세스입니다. 이렇게 하면 문서에 실제로 사용된 문자를 표시하는 데 필요한 글꼴 데이터만 포함되어 PDF 파일의 크기가 줄어듭니다.

#### Q: 전체 글꼴 포함과 글꼴 하위 집합 포함의 차이점은 무엇입니까?
A: 전체 글꼴 포함은 문서에 사용된 모든 글꼴을 PDF 파일에 포함하는 것을 의미합니다. 이렇게 하면 문서가 디자인된 대로 정확하게 표시되지만 PDF 파일의 크기가 커질 수 있습니다. 이와 대조적으로 글꼴 하위 집합을 포함하면 문서에 사용된 글리프만 포함되므로 PDF 파일의 크기가 줄어들지만 나중에 추가 문자가 추가될 경우 문서의 모양을 정확하게 복제하는 기능이 제한됩니다.

#### Q: .NET용 Aspose.Words를 사용하여 PDF 문서에 글꼴 하위 집합을 어떻게 포함할 수 있나요?
A: .NET용 Aspose.Words를 사용하여 PDF 문서에 글꼴 하위 집합을 포함하려면 다음 단계를 따르세요.

 교체하여 문서 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로로.

 다음을 사용하여 처리하려는 문서를 로드합니다.`Document` 클래스와 문서 경로.

 인스턴스를 생성하여 PDF 저장 옵션을 구성합니다.`PdfSaveOptions` 수업과 설정`EmbedFullFonts`재산`false`이렇게 하면 문서에 사용된 글꼴 하위 집합만 PDF 파일에 포함됩니다.

 다음을 사용하여 글꼴 하위 집합이 포함된 PDF 형식으로 문서를 저장합니다.`Save` 의 방법`Document` 객체, 출력 파일의 이름과 이전에 구성한 저장 옵션을 지정합니다.

#### Q: PDF 문서에 글꼴 하위 집합을 포함하면 어떤 이점이 있습니까?
A: PDF 문서에 글꼴 하위 집합을 포함하면 다음과 같은 이점이 있습니다.

PDF 파일 크기 감소: 문서에 사용된 글리프만 포함하면 전체 글꼴을 포함하는 것에 비해 PDF 파일 크기가 줄어듭니다.

문서 모양 보존: PDF 파일에 포함된 글꼴의 하위 집합을 사용하면 실제로 사용된 문자만 사용하여 문서의 모양을 재현할 수 있습니다.

라이센스 제한 사항과의 호환성: 라이센스 제한으로 인해 전체 글꼴을 합법적으로 포함할 수 없는 경우 글꼴의 하위 집합을 포함하는 것이 선호될 수 있습니다.