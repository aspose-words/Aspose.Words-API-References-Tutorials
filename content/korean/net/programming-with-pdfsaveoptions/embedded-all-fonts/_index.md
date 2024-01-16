---
title: PDF 문서에 글꼴 포함
linktitle: PDF 문서에 글꼴 포함
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF에 글꼴을 포함하는 방법에 대한 단계별 안내입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

이 문서에서는 .NET용 Aspose.Words의 PDF 문서 기능에 포함 글꼴을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드 조각을 살펴보고 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 문서에 모든 글꼴을 포함하는 방법과 .NET용 Aspose.Words를 사용하여 포함된 글꼴이 포함된 PDF를 생성하는 방법을 이해할 수 있을 것입니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리가 설치 및 설정되어 있는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 문서 디렉터리 경로 정의

 시작하려면 문서가 있는 디렉터리의 경로를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 넣기

다음으로 처리하려는 문서를 로드해야 합니다. 이 예에서는 문서 이름이 "Rendering.docx"이고 지정된 문서 디렉터리에 있다고 가정합니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: PDF 저장 옵션 구성

 결과 PDF에 모든 글꼴을 포함하려면 다음을 구성해야 합니다.`PdfSaveOptions` 이의를 제기하다`EmbedFullFonts` 다음으로 설정된 속성`true`. 이렇게 하면 문서에 사용된 모든 글꼴이 생성된 PDF 파일에 포함됩니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## 4단계: 문서를 포함된 글꼴이 있는 PDF로 저장

 마지막으로 문서를 글꼴이 포함된 PDF 파일로 저장할 수 있습니다. 출력 파일 이름을 지정하고`saveOptions` 이전 단계에서 구성한 개체입니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

그게 다야! 문서에 모든 글꼴을 성공적으로 포함하고 .NET용 Aspose.Words를 사용하여 포함된 글꼴이 포함된 PDF를 생성했습니다.

### .NET용 Aspose.Words를 사용하는 내장된 모든 글꼴의 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// 출력 PDF에는 문서에 있는 모든 글꼴이 포함됩니다.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF 문서에 모든 글꼴을 포함하는 방법을 배웠습니다. 글꼴을 포함하면 PDF가 열리는 시스템에 글꼴이 설치되지 않은 경우에도 문서에 지정된 글꼴을 사용할 수 있고 올바르게 표시할 수 있습니다. 이를 통해 다양한 장치와 플랫폼에서 일관된 모양과 정확한 문서 형식이 보장됩니다. .NET용 Aspose.Words의 더 많은 기능을 자유롭게 탐색하여 포함된 글꼴이 있는 PDF 문서 생성을 최적화하세요.

### 자주 묻는 질문

#### Q: PDF 문서에 글꼴을 포함한다는 것은 무엇이며 왜 중요한가요?
답변: PDF 문서에 글꼴을 포함시키는 것은 문서에 사용된 모든 글꼴을 PDF 파일 자체에 포함시키는 과정입니다. 이렇게 하면 PDF가 열리는 시스템에 글꼴이 설치되지 않은 경우에도 문서에 지정된 글꼴을 사용할 수 있고 올바르게 표시할 수 있습니다. 글꼴 포함은 문서의 모양과 서식을 유지하여 다양한 장치와 플랫폼에서 글꼴이 일관되게 렌더링되도록 하는 데 중요합니다.

#### Q: Aspose.Words for .NET을 사용하여 PDF 문서에 모든 글꼴을 어떻게 포함할 수 있나요?
A: .NET용 Aspose.Words를 사용하여 PDF 문서에 모든 글꼴을 포함하려면 다음 단계를 따르세요.

 교체하여 문서 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로로.

 다음을 사용하여 처리하려는 문서를 로드합니다.`Document` 클래스와 문서 경로.

 인스턴스를 생성하여 PDF 저장 옵션을 구성합니다.`PdfSaveOptions` 수업과 설정`EmbedFullFonts`재산`true`. 이렇게 하면 문서에 사용된 모든 글꼴이 생성된 PDF 파일에 포함됩니다.

 다음을 사용하여 글꼴이 포함된 PDF 형식으로 문서를 저장합니다.`Save` 의 방법`Document`객체, 출력 파일의 이름과 이전에 구성한 저장 옵션을 지정합니다.

#### Q: PDF 문서에 모든 글꼴을 포함하는 것이 왜 중요한가요?
답변: PDF가 열려 있는 시스템에서 지정된 글꼴을 사용할 수 없는 경우에도 문서가 올바르게 표시되도록 하려면 PDF 문서에 모든 글꼴을 포함시키는 것이 중요합니다. 이를 통해 문서의 모양, 서식 및 가독성을 유지하고 사용된 글꼴이 다양한 장치와 플랫폼에서 일관되게 렌더링되도록 할 수 있습니다.

#### Q: PDF 문서에 글꼴을 포함하면 어떤 이점이 있습니까?
A: PDF 문서에 글꼴을 포함하면 다음과 같은 이점이 있습니다.

일관된 문서 모양 보장: 내장된 글꼴은 시스템에서 사용 가능한 글꼴에 관계없이 문서가 디자인된 대로 정확하게 표시되도록 보장합니다.

서식 보존: 포함된 글꼴은 문서 서식과 레이아웃을 보존하여 글꼴 대체 및 모양 변형을 방지합니다.

가독성 향상: 원본 글꼴을 사용할 수 없더라도 지정된 글꼴을 사용하여 텍스트를 표시하므로 글꼴을 포함하면 문서의 가독성이 높아집니다.

#### Q: 모든 글꼴을 포함하면 PDF 파일의 크기가 커지나요?
A: 예, PDF 문서에 모든 글꼴을 포함하면 글꼴 데이터가 파일에 포함되어야 하므로 생성된 PDF 파일의 크기가 커질 수 있습니다. 그러나 이러한 크기 증가는 일반적으로 대부분의 문서에서 무시할 수 있으며 글꼴 포함의 이점은 크기가 약간 증가하는 것보다 더 큰 경우가 많습니다.

#### 질문: PDF 문서에 포함할 특정 글꼴을 선택할 수 있습니까?
 A: 예, Aspose.Words for .NET을 사용하면 고급 구성 옵션을 사용하여 PDF 문서에 포함할 특정 글꼴을 선택할 수 있습니다. 예를 들어 다음을 사용할 수 있습니다.`SubsetFonts` 의 재산`PdfSaveOptions` 개체를 사용하여 포함할 글꼴을 지정하거나 추가 옵션을 사용하여 사용자 정의 글꼴 선택 필터를 설정할 수 있습니다.