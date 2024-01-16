---
title: Word 문서 구조를 PDF 문서로 내보내기
linktitle: Word 문서 구조를 PDF 문서로 내보내기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서 구조를 PDF 문서로 내보내기에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/export-document-structure/
---

이 문서에서는 Aspose.Words for .NET에서 Word 문서 구조를 PDF 문서로 내보내기 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 문서 구조를 내보내고 문서 구조가 보이는 PDF를 생성하는 방법을 이해할 수 있습니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 문서 디렉터리 정의

 시작하려면 문서가 있는 디렉터리의 경로를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 업로드

다음으로 처리하려는 문서를 로드해야 합니다. 이 예에서는 문서가 "Paragraphs.docx"이고 지정된 문서 디렉터리에 있다고 가정합니다.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## 3단계: PDF로 저장 옵션 구성

 PDF 파일을 편집하는 동안 문서 구조를 내보내고 Adobe Acrobat Pro의 "콘텐츠" 탐색 창에 구조를 표시하려면 다음을 구성해야 합니다.`PdfSaveOptions` 이의를 제기하다`ExportDocumentStructure` 다음으로 설정된 속성`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## 4단계: 문서 구조를 사용하여 문서를 PDF로 저장

마지막으로 이전에 구성한 저장 옵션을 사용하여 문서를 PDF 형식으로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

그게 다야 ! Aspose.Words for .NET을 사용하여 문서 구조를 성공적으로 내보내고 문서 구조가 표시되는 PDF를 생성했습니다.

### .NET용 Aspose.Words를 사용하여 문서 구조를 내보내기 위한 샘플 소스 코드


```csharp

            // 문서 디렉터리의 경로입니다.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // 파일 크기가 늘어나고 "콘텐츠" 탐색 창에 구조가 표시됩니다.
            // Adobe Acrobat Pro의 .pdf를 편집하는 동안.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 구조를 PDF 문서로 내보내는 방법을 설명했습니다. 설명된 단계를 따르면 문서 구조가 표시된 PDF를 쉽게 생성할 수 있으므로 문서를 더 쉽게 탐색하고 검색할 수 있습니다. .NET용 Aspose.Words의 기능을 사용하여 Word 문서의 구조를 내보내고 잘 구조화된 PDF를 만드세요.

### 자주 묻는 질문

#### Q: Word 문서의 구조를 PDF 문서로 내보내는 것은 무엇입니까?
답변: Word 문서의 구조를 PDF 문서로 내보내면 문서 구조가 보이는 PDF가 생성됩니다. 문서 구조에는 일반적으로 문서의 제목, 섹션, 단락 및 기타 구조화된 요소가 포함됩니다. 이 구조는 PDF 문서 탐색 및 검색에 유용할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서의 구조를 PDF 문서로 내보내려면 어떻게 해야 합니까?
A: .NET용 Aspose.Words를 사용하여 Word 문서의 구조를 PDF 문서로 내보내려면 다음 단계를 따르세요.

 인스턴스를 생성합니다.`Document` Word 문서의 경로를 지정하는 클래스입니다.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 설정하고`ExportDocumentStructure`재산`true`. 이렇게 하면 문서 구조가 내보내지고 PDF 파일을 편집할 때 Adobe Acrobat Pro의 "콘텐츠" 탐색 창에 표시됩니다.

 사용`Save` 의 방법`Document`저장 옵션을 지정하여 문서를 PDF 형식으로 저장하는 클래스입니다.

#### 질문: Adobe Acrobat Pro를 사용하여 PDF 문서의 구조를 보려면 어떻게 해야 합니까?
A: Adobe Acrobat Pro를 사용하여 PDF 문서의 구조를 보려면 다음 단계를 따르십시오.

Adobe Acrobat Pro에서 PDF 문서를 엽니다.

왼쪽 탐색 모음에서 "콘텐츠" 아이콘을 클릭하여 "콘텐츠" 탐색 창을 표시합니다.

"콘텐츠" 탐색 창에는 제목, 섹션 및 기타 구조화된 요소가 포함된 문서 구조가 표시됩니다.