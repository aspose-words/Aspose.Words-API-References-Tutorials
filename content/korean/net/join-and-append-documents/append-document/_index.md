---
title: 문서 추가
linktitle: 문서 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 한 문서의 내용을 다른 문서에 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/append-document/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 한 문서의 내용을 다른 문서에 추가하는 방법을 설명합니다. 제공된 소스 코드는 소스 및 대상 문서를 열고 소스 문서의 섹션을 대상 문서로 가져오고 추가하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 있는 문서 디렉터리 경로입니다.

## 2단계: 원본 및 대상 문서 열기

 다음을 사용하여 원본 및 대상 문서를 엽니다.`Document` 클래스 생성자. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: 원본 문서의 섹션을 대상 문서에 추가

 원본 문서의 모든 섹션을 반복하고 다음을 사용하여 각 섹션을 대상 문서로 가져옵니다.`ImportNode` 방법. 그런 다음 가져온 섹션을 대상 문서에 추가합니다.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## 4단계: 대상 문서 저장

 마지막으로 다음을 사용하여 수정된 대상 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 문서 추가 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하는 Append Document의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// 소스 문서의 모든 섹션을 반복합니다.
	//섹션 노드는 Document 노드의 직계 자식이므로 Document만 열거할 수 있습니다.
	foreach (Section srcSection in srcDoc)
	{
		// 한 문서의 섹션을 다른 문서로 복사하기 때문에
		// 섹션 노드를 대상 문서로 가져와야 합니다.
		// 스타일, 목록 등에 대한 문서별 참조를 조정합니다.
		//
		// 노드를 가져오면 원래 노드의 복사본이 생성되지만 복사본은
		// 이제 대상 문서에 삽입할 준비가 되었습니다.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// 이제 새 섹션 노드를 대상 문서에 추가할 수 있습니다.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```