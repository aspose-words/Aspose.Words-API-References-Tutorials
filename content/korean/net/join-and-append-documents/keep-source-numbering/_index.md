---
title: 소스 번호 유지
linktitle: 소스 번호 유지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 소스 번호 지정 형식을 유지하면서 문서를 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/keep-source-numbering/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 번호가 매겨진 단락의 원래 번호 매기기 형식을 유지하면서 소스 문서를 대상 문서에 추가하는 방법을 설명합니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 저장될 문서 디렉터리 경로입니다.

## 2단계: 대상 및 원본 문서 만들기

 인스턴스 생성`Document` 대상 및 원본 문서의 경우.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: 가져올 때 소스 번호 유지

 소스 문서에서 번호가 매겨진 단락의 번호 매기기 서식을 유지하려면`ImportFormatOptions` 그리고 설정`KeepSourceNumbering` 에게`true` . 사용`NodeImporter` 소스 문서에서 대상 문서로 노드를 가져오고 지정`ImportFormatMode.KeepSourceFormatting` 그리고`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 4단계: 단락 가져오기 및 추가

원본 문서의 단락을 반복하고 다음을 사용하여 각 단락을 대상 문서로 가져옵니다.`importer`. 가져온 노드를 대상 문서의 본문에 추가합니다.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 5단계: 수정된 문서 저장

 다음을 사용하여 수정된 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

이로써 Aspose.Words for .NET을 사용하여 원래 번호 매기기 형식을 유지하면서 소스 문서를 대상 문서에 추가하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 소스 번호 유지에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// 번호가 매겨진 단락을 가져올 때 소스 목록 형식을 유지합니다.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```