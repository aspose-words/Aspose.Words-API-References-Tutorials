---
title: 콘텐츠 제어 색상 설정
linktitle: 콘텐츠 제어 색상 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 콘텐츠 컨트롤의 색상을 설정하고 모양을 사용자 지정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/set-content-control-color/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 콘텐츠 컨트롤의 색상을 설정하는 방법을 설명합니다. 색상을 변경하여 콘텐츠 컨트롤의 모양을 사용자 지정할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드 및 콘텐츠 컨트롤 검색
 다음을 사용하여 Word 문서를 로드합니다.`Document` 생성자, 문서 경로를 매개변수로 전달합니다. 문서에서 원하는 콘텐츠 컨트롤을 검색합니다. 이 예에서는 콘텐츠 컨트롤이 문서의 첫 번째 구조화된 문서 태그라고 가정합니다.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3단계: 콘텐츠 컨트롤 색상 설정
 할당하여 콘텐츠 컨트롤의 색상을 설정합니다.`Color` 가치를`Color` 구조화된 문서 태그의 속성입니다. 이 예에서는 색상을 빨간색으로 설정했습니다.

```csharp
sdt.Color = Color.Red;
```

## 4단계: 문서 저장
 수정된 문서를 다음을 사용하여 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.SetContentControlColor.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### .NET용 Aspose.Words를 사용하여 콘텐츠 제어 색상 설정에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 콘텐츠 컨트롤의 색상을 성공적으로 설정했습니다.