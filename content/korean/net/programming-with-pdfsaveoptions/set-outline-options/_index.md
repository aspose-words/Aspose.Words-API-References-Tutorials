---
title: PDF 문서의 개요 옵션 설정
linktitle: PDF 문서의 개요 옵션 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF 문서에서 개요 옵션을 설정하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/set-outline-options/
---

이 문서에서는 Aspose.Words for .NET에서 개요 옵션 설정을 메타파일 크기 기능으로 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 문서에서 개요 옵션을 설정하고 해당 개요 옵션을 사용하여 PDF를 생성하는 방법을 이해할 수 있습니다.

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

## 3단계: 계획 옵션을 사용하여 PDF로 저장 옵션 구성

생성된 PDF에서 개요 옵션을 설정하려면`PdfSaveOptions` 물체. 제목 개요 수준의 수를 설정할 수 있습니다(`HeadingsOutlineLevels`) 및 확장된 개요 수준 수(`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## 4단계: 개요 옵션을 사용하여 문서를 PDF로 저장

마지막으로 이전에 구성한 저장 옵션을 사용하여 문서를 PDF 형식으로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

그게 다야 ! 문서의 개요 옵션을 성공적으로 설정하고 Aspose.Words for .NET을 사용하여 해당 개요 옵션이 포함된 PDF를 생성했습니다.

### .NET용 Aspose.Words를 사용하여 계획 옵션을 메타파일 크기로 설정하는 예제 소스 코드


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF 문서에서 개요 옵션을 설정하는 방법을 설명했습니다. 설명된 단계를 사용하면 문서의 제목과 개요 수준을 쉽게 지정하고 해당 개요 옵션이 포함된 PDF 파일을 생성할 수 있습니다. .NET용 Aspose.Words를 사용하여 PDF 문서의 구조와 탐색을 개선하는 개요 옵션의 이점을 누려보세요.

### 자주 묻는 질문

#### Q: PDF 문서의 개요 옵션은 무엇입니까?
답변: PDF 문서의 개요 옵션은 문서 콘텐츠의 계층 구조를 나타냅니다. 이를 통해 대화형 목차를 생성하고 문서 탐색을 용이하게 할 수 있습니다. 개요 옵션은 개요에 포함할 제목 및 부제 수준과 생성된 개요에 표시할 세부 정보 수준을 결정합니다.

#### Q: Aspose.Words for .NET을 사용하여 PDF 문서에서 개요 옵션을 어떻게 설정할 수 있습니까?
A: .NET용 Aspose.Words를 사용하여 PDF 문서에서 개요 옵션을 설정하려면 다음 단계를 따르세요.

 교체하여 문서가 있는 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로로.

 PDF로 변환하려는 문서를 로드합니다.`Document` 클래스를 지정하고 지정된 문서 디렉터리에 있는 문서의 경로를 지정합니다.

 인스턴스를 생성하여 PDF로 저장 옵션을 구성합니다.`PdfSaveOptions` 수업과 사용`OutlineOptions` 개요 옵션을 설정하는 속성입니다. 다음을 사용하여 개요에 포함할 제목 수준 수를 지정할 수 있습니다.`HeadingsOutlineLevels` 속성과 확장된 개요 수준의 수를 사용하여`ExpandedOutlineLevels` 재산.

 다음을 사용하여 문서를 PDF 형식으로 저장합니다.`Save` 의 방법`Document` 경로와 저장 옵션을 지정하는 클래스입니다.

#### Q: PDF 문서의 계획 옵션은 무엇입니까?
답변: PDF 문서의 개요 옵션을 사용하면 콘텐츠의 계층적 구조를 생성할 수 있으므로 문서를 더 쉽게 탐색하고 다른 섹션에 액세스할 수 있습니다. 이를 통해 사용자는 목차나 개요의 항목을 클릭하여 문서의 특정 부분으로 빠르게 이동할 수 있습니다. 개요 옵션은 전체 문서 구조에 대한 개요를 제공하여 읽기 경험을 향상시킵니다.
