---
title: 구조화된 문서 태그 범위 시작 Xml 매핑
linktitle: 구조화된 문서 태그 범위 시작 Xml 매핑
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 XML 데이터를 Word의 구조화된 문서 태그에 동적으로 바인딩하는 방법을 알아보세요. 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## 소개

XML 데이터를 Word 문서에 동적으로 삽입하고 싶었던 적이 있습니까? 글쎄, 당신은 운이 좋다! .NET용 Aspose.Words를 사용하면 이 작업이 매우 간편해집니다. 이 튜토리얼에서는 구조화된 문서 태그 범위 시작 XML 매핑에 대해 자세히 살펴보겠습니다. 이 기능을 사용하면 사용자 지정 XML 부분을 콘텐츠 컨트롤에 바인딩하여 문서 콘텐츠가 XML 데이터와 원활하게 업데이트되도록 할 수 있습니다. 귀하의 문서를 역동적인 걸작으로 변화시킬 준비가 되었습니다.

## 전제 조건

코딩 부분으로 넘어가기 전에 필요한 모든 것이 갖추어져 있는지 확인하겠습니다.

1.  .NET 라이브러리용 Aspose.Words: 최신 버전이 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio 또는 C#을 지원하는 기타 IDE.
3. C#에 대한 기본 지식: C# 프로그래밍에 대한 지식이 필수입니다.
4. Word 문서: 작업할 샘플 Word 문서입니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이렇게 하면 .NET용 Aspose.Words의 모든 필수 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## 1단계: 문서 디렉토리 설정

모든 프로젝트에는 기초가 필요합니다. 그렇죠? 여기서는 문서 디렉터리 경로를 설정합니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: Word 문서 로드

다음으로 Word 문서를 로드합니다. 이것은 XML 데이터를 삽입할 문서입니다.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## 3단계: 사용자 정의 XML 부분 추가

삽입하려는 데이터가 포함된 XML 부분을 생성하고 이를 문서의 CustomXmlPart 컬렉션에 추가해야 합니다. 이 사용자 정의 XML 부분은 구조화된 문서 태그의 데이터 소스 역할을 합니다.

### XML 부분 만들기

먼저 XML 부분에 대한 고유 ID를 생성하고 해당 콘텐츠를 정의합니다.

```csharp
// 데이터가 포함된 XML 부분을 구성하고 이를 문서의 CustomXmlPart 컬렉션에 추가합니다.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### XML 부분 콘텐츠 확인

XML 부분이 올바르게 추가되었는지 확인하기 위해 해당 내용을 인쇄합니다.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## 4단계: 구조화된 문서 태그 생성

SDT(구조적 문서 태그)는 XML 부분에 바인딩할 수 있는 콘텐츠 컨트롤입니다. 여기서는 사용자 정의 XML 부분의 내용을 표시하는 SDT를 생성합니다.

먼저 문서에서 SDT 범위 시작을 찾습니다.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## 5단계: SDT에 대한 XML 매핑 설정

이제 XML 부분을 SDT에 바인딩할 차례입니다. XML 매핑을 설정하여 SDT에 표시되어야 하는 XML 데이터 부분을 지정합니다.

 XPath는 표시하려는 XML 부분의 특정 요소를 가리킵니다. 여기서 우리는 두 번째를 가리킨다.`<text>` 내의 요소`<root>` 요소.

```csharp
// StructuredDocumentTag에 대한 매핑 설정
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## 6단계: 문서 저장

마지막으로 문서를 저장하여 실제 변경 사항을 확인하세요. 이제 Word 문서의 SDT에 지정된 XML 콘텐츠가 표시됩니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## 결론

그리고 거기에 있습니다! Aspose.Words for .NET을 사용하여 Word 문서의 구조화된 문서 태그에 XML 부분을 성공적으로 매핑했습니다. 이 강력한 기능을 사용하면 동적인 데이터 기반 문서를 쉽게 만들 수 있습니다. 보고서, 송장 또는 기타 문서 유형을 생성하는 경우 XML 매핑을 통해 작업 흐름을 크게 간소화할 수 있습니다.

## FAQ

### Word의 구조화된 문서 태그란 무엇입니까?
콘텐츠 컨트롤이라고도 하는 구조화된 문서 태그는 Word 문서의 특정 콘텐츠 유형에 대한 컨테이너입니다. 데이터를 바인딩하고, 편집을 제한하고, 사용자에게 문서 작성을 안내하는 데 사용할 수 있습니다.

### XML 부분 콘텐츠를 동적으로 업데이트하려면 어떻게 해야 합니까?
 다음을 수정하여 XML 부분 콘텐츠를 업데이트할 수 있습니다.`xmlPartContent` 문서에 추가하기 전에 문자열입니다. 새로운 데이터로 문자열을 업데이트하고`CustomXmlParts` 수집.

### 여러 XML 부분을 동일한 문서의 다른 SDT에 바인딩할 수 있나요?
예, 여러 XML 부분을 동일한 문서의 다른 SDT에 바인딩할 수 있습니다. 각 SDT는 고유한 XML 부분과 XPath 매핑을 가질 수 있습니다.

### 복잡한 XML 구조를 SDT에 매핑하는 것이 가능합니까?
전적으로! XML 부분 내에서 원하는 요소를 정확하게 가리키는 자세한 XPath 표현식을 사용하여 복잡한 XML 구조를 SDT에 매핑할 수 있습니다.

### 문서에서 XML 부분을 제거하려면 어떻게 해야 합니까?
 다음을 호출하여 XML 부분을 제거할 수 있습니다.`Remove` 에 대한 방법`CustomXmlParts` 수집, 전달`xmlPartId` 제거하려는 XML 부분의