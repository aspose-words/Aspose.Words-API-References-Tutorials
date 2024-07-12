---
title: 콘텐츠 제어 스타일 설정
linktitle: 콘텐츠 제어 스타일 설정
second_title: Aspose.Words 문서 처리 API
description: 일관된 서식을 적용하여 .NET용 Aspose.Words를 사용하여 Word 문서에서 콘텐츠 컨트롤의 스타일을 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/set-content-control-style/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 콘텐츠 컨트롤의 스타일을 설정하는 방법을 설명합니다. 일관된 서식 지정을 위해 콘텐츠 컨트롤에 미리 정의된 스타일이나 사용자 지정 스타일을 적용할 수 있습니다.

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

## 3단계: 스타일 검색 및 콘텐츠 제어에 적용
 문서의 스타일 컬렉션에서 원하는 스타일을 검색합니다. 이 예에서는 다음을 사용하여 "인용문" 스타일을 검색합니다.`StyleIdentifier.Quote` . 그런 다음 검색된 스타일을`Style` 구조화된 문서 태그의 속성입니다.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## 4단계: 문서 저장
 수정된 문서를 다음을 사용하여 지정된 디렉터리에 저장합니다.`Save`방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.SetContentControlStyle.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### .NET용 Aspose.Words를 사용하여 콘텐츠 제어 스타일 설정에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 콘텐츠 컨트롤의 스타일을 성공적으로 설정했습니다.