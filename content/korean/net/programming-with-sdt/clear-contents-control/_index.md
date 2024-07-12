---
title: 컨텐츠 제어 지우기
linktitle: 컨텐츠 제어 지우기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 컨트롤의 내용을 지우는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/clear-contents-control/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 SDT의 내용을 지우는 방법을 보여줍니다. SDT의 콘텐츠를 지우면 콘텐츠 제어 내의 모든 텍스트나 하위 노드가 제거됩니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드 및 StructuredDocumentTag 가져오기
 다음을 사용하여 Word 문서를 로드합니다.`Document` 생성자, 문서 경로를 매개변수로 전달합니다. 그런 다음 원하는 것을 검색하십시오.`StructuredDocumentTag`문서에서. 이 예에서는 SDT가 문서의 첫 번째 하위 노드라고 가정합니다.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3단계: StructuredDocumentTag의 내용 지우기
 다음을 사용하여 SDT의 내용을 지웁니다.`Clear` 방법. 이렇게 하면 콘텐츠 컨트롤 내의 모든 텍스트나 하위 노드가 제거됩니다.

```csharp
sdt.Clear();
```

## 4단계: 문서 저장
 다음을 사용하여 수정된 문서를 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.ClearContentsControl.doc"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### .NET용 Aspose.Words를 사용하는 Clear Contents Control의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 StructuredDocumentTag의 내용을 성공적으로 지웠습니다.