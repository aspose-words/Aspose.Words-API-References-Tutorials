---
title: PDF 문서의 마지막 인쇄 속성 업데이트
linktitle: PDF 문서의 마지막 인쇄 속성 업데이트
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 "마지막 인쇄" 속성을 업데이트하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

이 문서에서는 Aspose.Words for .NET에서 PDF 문서 업데이트 기능의 "마지막 인쇄" 속성을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 PDF로 변환할 때 "마지막 인쇄" 속성을 업데이트하는 옵션을 구성하는 방법을 이해할 수 있습니다.

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

## 3단계: 업데이트된 "마지막 인쇄" 속성을 사용하여 PDF로 저장 옵션 구성

 PDF로 변환할 때 "마지막 인쇄" 속성 업데이트를 활성화하려면 다음을 구성해야 합니다.`PdfSaveOptions` 객체를 설정하고`UpdateLastPrintedProperty`재산`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## 4단계: "마지막 인쇄" 속성을 업데이트하여 문서를 PDF로 저장합니다.

마지막으로 이전에 구성한 저장 옵션을 사용하여 문서를 PDF 형식으로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

그게 다야 ! .NET용 Aspose.Words를 사용하여 문서를 PDF로 변환할 때 "마지막 인쇄" 속성 업데이트를 성공적으로 활성화했습니다.

### .NET용 Aspose.Words를 사용하여 "마지막 인쇄" 속성을 업데이트하기 위한 예제 소스 코드


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF 문서에서 "마지막 인쇄" 속성을 업데이트하는 방법을 설명했습니다. 주어진 단계를 따르면 문서를 PDF로 변환할 때 "마지막 인쇄" 속성을 업데이트하는 옵션을 쉽게 구성할 수 있습니다. 이 기능을 사용하면 문서 사용 및 관련 정보를 추적할 수 있습니다.

### 자주 묻는 질문

#### Q: PDF 문서의 "마지막 인쇄" 속성은 무엇입니까?
답변: PDF 문서의 "마지막 인쇄" 속성은 문서가 마지막으로 인쇄된 날짜와 시간을 나타냅니다. 이 속성은 문서 사용 및 관리에 대한 정보를 추적하는 데 유용할 수 있습니다.

#### Q: .NET용 Aspose.Words를 사용하여 PDF 문서의 "마지막 인쇄" 속성을 어떻게 업데이트할 수 있습니까?
A: .NET용 Aspose.Words를 사용하여 PDF 문서의 "마지막 인쇄" 속성을 업데이트하려면 다음 단계를 따르세요.

 인스턴스를 생성합니다.`Document` Word 문서의 경로를 지정하는 클래스입니다.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 설정하고`UpdateLastPrintedProperty`재산`true` "마지막 인쇄" 속성 업데이트를 활성화합니다.

 사용`Save` 의 방법`Document`저장 옵션을 지정하여 문서를 PDF 형식으로 저장하는 클래스입니다.

#### Q: 생성된 PDF 문서에서 "마지막 인쇄" 속성이 업데이트되었는지 어떻게 확인할 수 있습니까?
A: Adobe Acrobat Reader와 같은 호환 가능한 PDF 뷰어로 PDF 파일을 열고 문서 정보를 보면 생성된 PDF 문서에서 "마지막 인쇄" 속성이 업데이트되었는지 확인할 수 있습니다. 마지막 인쇄 날짜 및 시간은 PDF 문서 생성 날짜 및 시간과 일치해야 합니다.
