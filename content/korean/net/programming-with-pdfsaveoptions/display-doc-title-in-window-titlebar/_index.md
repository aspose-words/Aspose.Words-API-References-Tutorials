---
title: 창 제목 표시줄에 문서 제목 표시
linktitle: 창 제목 표시줄에 문서 제목 표시
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 창 제목 표시줄에 문서 제목을 표시하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 창 제목 표시줄에 문서 제목을 표시하는 단계를 안내합니다. 이 기능을 사용하면 생성된 PDF 문서를 열 때 창 제목 표시줄에 문서 제목을 표시할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드

PDF로 변환하려는 문서를 업로드하여 시작하십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

문서의 올바른 경로를 지정해야 합니다.

## 2단계: PDF 저장 옵션 구성

PdfSaveOptions 클래스의 인스턴스를 만들고 창 제목 표시줄에 문서 제목 표시를 활성화합니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

이 옵션을 사용하면 PDF로 변환할 때 창 제목 표시줄에 문서 제목을 표시할 수 있습니다.

## 3단계: 문서를 PDF로 변환

 사용`Save` 변환 옵션을 지정하여 문서를 PDF로 변환하는 방법:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

변환된 PDF를 저장할 올바른 경로를 지정했는지 확인하세요.

### .NET용 Aspose.Words를 사용하여 창 제목 표시줄에 문서 제목 표시에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 PDF 문서의 창 제목 표시줄에 문서 제목을 표시하는 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
다음 단계를 따르면 Aspose.Words for .NET을 사용하여 PDF로 변환할 때 창 제목 표시줄에 문서 제목을 쉽게 표시할 수 있습니다.

### 자주 묻는 질문

#### Q: Aspose.Words for .NET의 "창 제목 표시줄에 문서 제목 표시" 기능은 무엇입니까?
.NET용 Aspose.Words의 "창 제목 표시줄에 문서 제목 표시" 기능을 사용하면 생성된 PDF 문서를 열 때 창 제목 표시줄에 문서 제목을 표시할 수 있습니다. 이를 통해 읽기 환경에서 PDF 문서를 더 쉽게 식별하고 구별할 수 있습니다.

#### Q: .NET용 Aspose.Words에서 이 기능을 어떻게 사용할 수 있나요?
.NET용 Aspose.Words에서 이 기능을 사용하려면 다음 단계를 따르세요.

 다음을 사용하여 문서를 로드합니다.`Document` 방법을 사용하고 PDF로 변환할 파일의 경로를 지정합니다.

 인스턴스를 생성하여 PDF 저장 옵션을 구성합니다.`PdfSaveOptions` 수업과 설정`DisplayDocTitle`재산`true`. 이를 통해 PDF로 변환할 때 창 제목 표시줄에 문서 제목을 표시할 수 있습니다.

 사용`Save` 변환 옵션을 지정하여 문서를 PDF로 변환하는 방법입니다.

#### Q: 이 기능을 사용하면 문서 자체의 내용이 변경되나요?
아니요. 이 기능은 문서 자체의 내용을 수정하지 않습니다. PDF 문서로 열릴 때 창 제목 표시줄의 문서 제목 표시에만 영향을 미칩니다. 문서의 내용은 변경되지 않습니다.

#### Q: 창의 제목 표시줄에 표시되는 문서의 제목을 사용자 정의할 수 있나요?
 예, 창 제목 표시줄에 표시되는 문서 제목을 사용자 정의할 수 있습니다.`Document.Title` PDF로 변환하기 전에 문서의 속성을 변경하세요. 문자열을 사용하여 원하는 제목을 설정할 수 있습니다. 전화하기 전에 반드시 제목을 설정하세요.`Save` PDF로 변환하는 방법.

#### Q: Aspose.Words는 문서 변환을 위해 어떤 다른 출력 형식을 지원합니까?
Aspose.Words for .NET은 PDF, XPS, HTML, EPUB, MOBI, 이미지(JPEG, PNG, BMP, TIFF, GIF) 등과 같은 문서 변환을 위한 다양한 출력 형식을 지원합니다. 아직도 다른 사람들. 특정 요구 사항에 따라 적절한 출력 형식을 선택할 수 있습니다.