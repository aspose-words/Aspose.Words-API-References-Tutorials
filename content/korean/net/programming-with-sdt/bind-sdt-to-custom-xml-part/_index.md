---
title: SDT를 사용자 정의 Xml 부분에 바인딩
linktitle: SDT를 사용자 정의 Xml 부분에 바인딩
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 SDT를 사용자 정의 Xml 부분에 바인딩하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 SDT(구조적 문서 태그)를 사용자 정의 Xml 부분에 바인딩하는 방법을 보여줍니다. SDT를 사용하면 Word 문서에 구조화된 콘텐츠 컨트롤을 추가할 수 있으며 CustomXmlParts는 문서와 관련된 사용자 지정 XML 데이터를 저장하는 방법을 제공합니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 XML에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 및 CustomXmlPart 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`CustomXmlPart` 사용자 정의 XML 데이터를 저장합니다. 사용자 정의 XML은 유효한 XML 형식이어야 합니다. 이 예에서는 간단한 XML 문자열을 사용합니다.`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## 3단계: 문서에 SDT(StructuredDocumentTag) 추가
 을 추가하다`StructuredDocumentTag` 콘텐츠 제어 역할을 하는 문서에 추가합니다. 지정`SdtType` ~처럼`PlainText` 그리고`MarkupLevel` ~처럼`Block` 블록 수준 SDT를 생성합니다.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## 4단계: SDT에 대한 XML 매핑 설정
 SDT를 다음과 같이 매핑합니다.`CustomXmlPart` 을 사용하여`SetMapping` 의 방법`XmlMapping` 재산. 지정`CustomXmlPart` , 원하는 XML 노드를 찾기 위한 XPath 표현식, 필요한 경우 네임스페이스 접두사. 이 예에서는 SDT를 다음과 같이 매핑합니다.`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## 5단계: 문서 저장
 수정된 문서를 다음을 사용하여 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.BindSDTtoCustomXmlPart.doc"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### .NET용 Aspose.Words를 사용하여 Sd Tto 사용자 정의 Xml 부분 바인딩에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서의 CustomXmlPart에 SDT를 성공적으로 바인딩했습니다.