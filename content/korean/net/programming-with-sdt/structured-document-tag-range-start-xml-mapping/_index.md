---
title: 구조화된 문서 태그 범위 시작 Xml 매핑
linktitle: 구조화된 문서 태그 범위 시작 Xml 매핑
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 구조화된 문서 태그 범위 시작에 대한 XML 매핑을 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 구조화된 문서 태그 범위 시작에 대한 XML 매핑을 설정하는 방법을 설명합니다. XML 매핑을 사용하면 콘텐츠 컨트롤 내에서 XML 데이터 소스의 특정 부분을 표시할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드 및 XML 부분 만들기
 다음을 사용하여 Word 문서를 로드합니다.`Document`생성자, 문서 경로를 매개변수로 전달합니다. 구조화된 문서 태그 내에 표시할 데이터가 포함된 XML 부분을 만듭니다.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## 3단계: 구조화된 문서 태그에 대한 XML 매핑 설정
문서에서 구조화된 문서 태그 범위 시작을 검색합니다. 그런 다음 XPath 표현식을 사용하여 사용자 정의 XML 부분의 특정 부분을 표시하도록 구조화된 문서 태그에 대한 XML 매핑을 설정합니다.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## 4단계: 문서 저장
 수정된 문서를 다음을 사용하여 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### 구조화된 문서 태그 범위에 대한 예제 소스 코드 .NET용 Aspose.Words를 사용하여 Xml 매핑 시작 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// 데이터가 포함된 XML 부분을 구성하고 이를 문서의 CustomXmlPart 컬렉션에 추가합니다.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// 문서에 CustomXmlPart의 내용을 표시하는 StructuredDocumentTag를 만듭니다.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// StructuredDocumentTag에 대한 매핑을 설정하면
	//XPath가 가리키는 CustomXmlPart의 일부만 표시됩니다.
	// 이 XPath는 CustomXmlPart의 첫 번째 "<root>" 요소 중 두 번째 "<text>" 요소의 내용을 가리킵니다.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 구조화된 문서 태그 범위 시작에 대한 XML 매핑을 성공적으로 설정했습니다.