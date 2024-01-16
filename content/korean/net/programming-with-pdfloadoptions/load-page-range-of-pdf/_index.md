---
title: PDF의 페이지 범위 로드
linktitle: PDF의 페이지 범위 로드
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 특정 PDF 페이지 범위를 로드하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF 문서에서 특정 페이지 범위를 로드하는 방법을 안내합니다. 아래 단계를 따르십시오.

## 1단계: 다양한 PDF 페이지 로드

PDF 문서에서 특정 페이지 범위를 로드하려면 다음 코드를 사용하십시오.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 이 예에서는 PDF 문서의 첫 번째 페이지를 로드합니다. 값을 변경할 수 있습니다.`PageIndex` 그리고`PageCount` 원하는 페이지 범위로 이동합니다.

## 2단계: 문서 저장

 마지막으로 다음을 사용하여 특정 페이지 범위가 포함된 문서를 저장할 수 있습니다.`Save` 방법:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

편집된 문서를 저장하려면 올바른 경로를 지정해야 합니다.

그게 다야 ! 이제 .NET용 Aspose.Words를 사용하여 PDF 문서에서 특정 페이지 범위를 로드했습니다.

### .NET용 Aspose.Words를 사용하여 PDF 페이지 범위 로드에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
PDF 문서 디렉토리의 올바른 경로를 지정하는 것을 잊지 마십시오.



