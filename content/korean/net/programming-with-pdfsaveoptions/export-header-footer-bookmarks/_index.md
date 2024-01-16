---
title: Word 문서 머리글 바닥글 책갈피를 PDF 문서로 내보내기
linktitle: Word 문서 머리글 바닥글 책갈피를 PDF 문서로 내보내기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 단어 문서 머리글 바닥글 책갈피를 PDF 문서 책갈피로 내보내는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

이 문서에서는 Aspose.Words for .NET을 사용하여 Word 문서 머리글 바닥글 책갈피를 PDF 문서 기능으로 내보내는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 문서의 머리글과 바닥글에서 책갈피를 내보내고 적절한 책갈피가 포함된 PDF를 생성하는 방법을 이해할 수 있습니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 문서 디렉터리 정의

 시작하려면 문서가 있는 디렉터리의 경로를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 업로드

다음으로 처리하려는 문서를 로드해야 합니다. 이 예에서는 문서 이름이 "머리글 및 바닥글의 책갈피.docx"이고 지정된 문서 디렉토리에 있다고 가정합니다.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## 3단계: PDF로 저장 옵션 구성

 머리글 및 바닥글 북마크를 내보내려면 다음을 구성해야 합니다.`PdfSaveOptions` 물체. 이 예에서는 기본 책갈피 개요 수준을 1로 설정하고 머리글 및 바닥글 책갈피 내보내기 모드를 "첫 번째"로 설정했습니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## 4단계: 머리글 및 바닥글 책갈피가 포함된 문서를 PDF로 저장

마지막으로 이전에 구성한 저장 옵션을 사용하여 문서를 PDF 형식으로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

그게 다야 ! 문서에서 머리글 및 바닥글 책갈피를 성공적으로 내보내고 .NET용 Aspose.Words를 사용하여 적절한 책갈피가 포함된 PDF를 생성했습니다.

### .NET용 Aspose.Words를 사용하여 머리글 및 바닥글 북마크를 내보내기 위한 샘플 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 머리글 및 바닥글 북마크를 PDF 문서로 내보내는 방법을 설명했습니다. 내보낸 북마크를 사용하면 생성된 PDF 문서의 해당 머리글과 바닥글을 쉽게 탐색하고 빠르게 참조할 수 있습니다. 문서에서 머리글 및 바닥글 북마크를 내보내고 Aspose.Words for .NET을 사용하여 적절한 북마크가 포함된 PDF를 생성하려면 설명된 단계를 따르세요. 문서의 올바른 경로를 지정하고 필요에 따라 저장 옵션을 구성하십시오.

### 자주 묻는 질문

### Q: 머리글 및 바닥글 책갈피를 Word 문서에서 PDF 문서로 내보내는 것은 무엇입니까?
A: 머리글 및 바닥글 책갈피를 Word 문서에서 PDF 문서로 내보내는 것은 머리글 및 바닥글에서 PDF 문서의 책갈피를 유지하고 생성하는 기능입니다. 원본 Word 문서의 바닥글. 이를 통해 사용자는 머리글과 바닥글에 해당하는 책갈피를 사용하여 PDF 문서를 빠르고 쉽게 탐색할 수 있습니다.

### Q: Aspose.Words for .NET을 사용하여 Word 문서의 머리글 및 바닥글 책갈피를 PDF 문서로 내보내려면 어떻게 해야 합니까?
A: .NET용 Aspose.Words를 사용하여 Word 문서의 머리글 및 바닥글 책갈피를 PDF 문서로 내보내려면 다음 단계를 따르세요.

 교체하여 문서가 있는 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로로.

 다음을 사용하여 처리하려는 문서를 로드합니다.`Document` 클래스를 지정하고 지정된 문서 디렉터리에 있는 Word 문서의 경로를 지정합니다.

 인스턴스를 생성하여 PDF로 저장 옵션을 구성합니다.`PdfSaveOptions` 클래스를 설정하고 적절한 머리글 및 바닥글 북마크 옵션을 설정합니다.

 다음을 사용하여 문서를 PDF 형식으로 저장합니다.`Save` 의 방법`Document` 경로와 저장 옵션을 지정하는 클래스입니다.

### Q: 머리글 및 바닥글 책갈피를 PDF 문서로 내보내면 어떤 이점이 있습니까?
A: 머리글 및 바닥글 책갈피를 PDF 문서로 내보내면 다음과 같은 이점이 있습니다.

쉬운 탐색: 북마크를 사용하면 사용자는 특정 머리글과 바닥글을 참조하여 PDF 문서를 쉽게 탐색할 수 있습니다.

빠른 참조: 책갈피를 사용하면 사용자는 머리글과 바닥글을 기반으로 PDF 문서의 관련 섹션을 빠르게 찾을 수 있습니다.