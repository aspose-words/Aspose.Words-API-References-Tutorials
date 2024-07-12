---
title: 사용자 지정 XML 부분에 매핑된 표 반복 구역 만들기
linktitle: 사용자 지정 XML 부분에 매핑된 표 반복 구역 만들기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 CustomXmlPart에 매핑된 반복 구역이 있는 테이블을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

이 자습서에서는 .NET용 Aspose.Words를 사용하여 Word 문서의 사용자 지정 Xml 부분에 매핑된 반복 구역이 있는 테이블을 만드는 방법을 보여줍니다. 반복 구역을 사용하면 사용자 정의 Xml 부분에 저장된 XML 데이터를 기반으로 행을 동적으로 추가할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"`문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 및 DocumentBuilder 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 문서의 내용을 작성합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: CustomXmlPart에 사용자 지정 XML 데이터 추가
 만들기`CustomXmlPart` 여기에 사용자 정의 XML 데이터를 추가합니다. 이 예에서는 제목과 저자가 포함된 책 모음을 나타내는 XML 문자열을 만듭니다.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## 4단계: 테이블 및 테이블 구조 만들기
 다음을 사용하여 테이블 생성을 시작합니다.`StartTable` 의 방법`DocumentBuilder` . 다음을 사용하여 표 셀과 내용을 추가합니다.`InsertCell`그리고`Write` 행동 양식.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## 5단계: 사용자 지정 XML에 매핑된 반복 구역 만들기
 만들기`StructuredDocumentTag` ~와 함께`SdtType.RepeatingSection` 반복되는 부분을 표현합니다. 다음을 사용하여 반복 구역에 대한 XML 매핑을 설정합니다.`SetMapping` 의 방법`XmlMapping` 재산. 이 예에서는 반복 섹션을 다음과 같이 매핑합니다.`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## 6단계: 반복 구역 항목 만들기 및 셀 추가
 만들기`StructuredDocumentTag` ~와 함께`SdtType.RepeatingSectionItem` 반복 구역 항목을 나타냅니다. 반복 구역에 하위 항목으로 추가합니다.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 만들기`Row` 반복 구역의 각 항목을 나타내고 이를 반복 구역 항목에 추가합니다.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## 7단계: 반복 구역 내에 콘텐츠 컨트롤 추가
 만들다`StructuredDocumentTag` 가진 물건`SdtType.PlainText`

  제목 및 작성자 콘텐츠 컨트롤을 나타냅니다. 다음을 사용하여 각 콘텐츠 컨트롤에 대한 XML 매핑을 설정합니다.`SetMapping` 의 방법`XmlMapping` 재산. 이 예에서는 제목 컨트롤을 다음에 매핑합니다.`/books[1]/book[1]/title[1]` 작성자는 다음을 제어합니다.`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## 8단계: 문서 저장
 수정된 문서를 다음을 사용하여 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### .NET용 Aspose.Words를 사용하여 사용자 정의 Xml 부분에 매핑된 테이블 반복 구역을 생성하기 위한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서의 CustomXmlPart에 매핑된 반복 구역이 있는 테이블을 성공적으로 만들었습니다.