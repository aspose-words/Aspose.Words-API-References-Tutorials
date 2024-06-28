---
title: 텍스트 상자 무시
linktitle: 텍스트 상자 무시
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 텍스트 상자 서식을 무시하면서 문서를 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/ignore-text-boxes/
---

이 튜토리얼에서는 텍스트 상자의 서식을 유지하면서 문서를 추가하기 위해 .NET용 Aspose.Words를 사용하는 방법을 설명합니다. 제공된 소스 코드는 추가 프로세스 중에 텍스트 상자를 포함하도록 가져오기 형식 옵션을 설정하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 있는 문서 디렉터리 경로입니다.

## 2단계: 원본 및 대상 문서 열기

 다음을 사용하여 원본 및 대상 문서를 엽니다.`Document` 클래스 생성자. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: 가져오기 형식 옵션 설정

 인스턴스를 생성합니다.`ImportFormatOptions` 클래스를 설정하고`IgnoreTextBoxes`재산`false`. 이렇게 하면 서식을 유지하면서 추가 프로세스 중에 텍스트 상자가 포함됩니다.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## 4단계: 텍스트 상자 내용 추가

 만들기`NodeImporter`개체를 사용하여 원본 문서의 텍스트 상자 노드를 대상 문서로 가져옵니다. 소스 문서의 각 단락을 반복하고 이를 대상 문서로 가져옵니다.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 5단계: 대상 문서 저장

마지막으로 다음을 사용하여 수정된 대상 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 텍스트 상자 서식을 유지하면서 문서 추가 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 텍스트 상자 무시에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// 가져올 때 소스 텍스트 상자 서식을 유지합니다.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```