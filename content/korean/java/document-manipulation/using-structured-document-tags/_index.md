---
title: Aspose.Words for Java에서 구조화된 문서 태그(SDT) 사용하기
linktitle: 구조화된 문서 태그(SDT) 사용
second_title: Aspose.Words Java 문서 처리 API
description: 이 포괄적인 가이드를 통해 Java용 Aspose.Words에서 구조화된 문서 태그(SDT)를 사용하는 방법을 알아보세요. SDT를 생성, 수정하고 사용자 정의 XML 데이터에 바인딩합니다.
type: docs
weight: 19
url: /ko/java/document-manipulation/using-structured-document-tags/
---

## Aspose.Words for Java에서 구조적 문서 태그(SDT) 사용 소개

구조화된 문서 태그(SDT)는 문서 내에서 구조화된 콘텐츠를 생성하고 조작할 수 있는 Aspose.Words for Java의 강력한 기능입니다. 이 포괄적인 가이드에서는 Aspose.Words for Java에서 SDT를 사용하는 다양한 측면을 안내합니다. 당신이 초보자이건 숙련된 개발자이건 이 글에서 귀중한 통찰력과 실제 사례를 발견할 수 있을 것입니다.

## 시작하기

세부 사항을 살펴보기 전에 환경을 설정하고 기본 SDT를 생성해 보겠습니다. 이 섹션에서는 다음 주제를 다룹니다.

- 새 문서 만들기
- 구조화된 문서 태그 추가
- 문서 저장

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// CHECKBOX 유형의 구조화된 문서 태그 생성
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// 문서 저장
doc.save("WorkingWithSDT.docx");
```

## 확인란 SDT의 현재 상태 확인

문서에 확인란 SDT를 추가한 후에는 프로그래밍 방식으로 현재 상태를 확인할 수 있습니다. 이는 사용자 입력의 유효성을 검사해야 하거나 체크박스 상태에 따라 특정 작업을 수행해야 할 때 유용할 수 있습니다.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // 체크박스가 선택되어 있습니다.
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## 콘텐츠 컨트롤 수정

이 섹션에서는 문서 내의 콘텐츠 컨트롤을 수정하는 방법을 살펴보겠습니다. 일반 텍스트, 드롭다운 목록 및 그림의 세 가지 유형의 콘텐츠 컨트롤을 다룹니다.

### 일반 텍스트 콘텐츠 제어 수정

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // 기존 콘텐츠 지우기
    sdtPlainText.removeAllChildren();

    // 새 텍스트 추가
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### 드롭다운 목록 콘텐츠 제어 수정

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // 목록에서 두 번째 항목을 선택하십시오.
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### 사진 콘텐츠 제어 수정

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // 이미지를 새 이미지로 교체하세요
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## ComboBox 콘텐츠 컨트롤 만들기

ComboBox 콘텐츠 컨트롤을 사용하면 사용자는 미리 정의된 옵션 목록에서 선택할 수 있습니다. 문서에서 하나를 만들어 보겠습니다.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## 서식 있는 텍스트 콘텐츠 제어 작업

서식 있는 텍스트 콘텐츠 컨트롤은 문서에 서식 있는 텍스트를 추가하는 데 적합합니다. 하나를 만들고 내용을 설정해 보겠습니다.

```java
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.setText("Hello World");
run.getFont().setColor(Color.GREEN);
para.getRuns().add(run);
sdtRichText.getChildNodes().add(para);
doc.getFirstSection().getBody().appendChild(sdtRichText);

doc.save("RichTextDocument.docx");
```

## 콘텐츠 제어 스타일 설정

콘텐츠 컨트롤에 스타일을 적용하여 문서의 시각적 모양을 향상시킬 수 있습니다. 콘텐츠 컨트롤의 스타일을 설정하는 방법을 살펴보겠습니다.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//사용자 정의 스타일 적용
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## SDT를 사용자 정의 XML 데이터에 바인딩

일부 시나리오에서는 동적 콘텐츠 생성을 위해 SDT를 사용자 정의 XML 데이터에 바인딩해야 할 수도 있습니다. 이를 달성하는 방법을 살펴보겠습니다.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## 사용자 정의 XML 데이터에 매핑된 반복 구역이 있는 표 만들기

반복 섹션이 있는 표는 구조화된 데이터를 표시하는 데 매우 유용할 수 있습니다. 이러한 테이블을 생성하고 이를 사용자 정의 XML 데이터에 매핑해 보겠습니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books", "<books>...</books>");
Table table = builder.startTable();
builder.insertCell();
builder.write("Title");
builder.insertCell();
builder.write("Author");
builder.endRow();
builder.endTable();

StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
table.appendChild(repeatingSectionSdt);

StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
repeatingSectionSdt.appendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.appendChild(row);

StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.appendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.appendChild(authorSdt);

doc.save("RepeatingTableDocument.docx");
```

## 다중 섹션 구조화된 문서 태그 작업

구조화된 문서 태그는 문서의 여러 섹션에 걸쳐 있을 수 있습니다. 이 섹션에서는 다중 섹션 SDT로 작업하는 방법을 살펴보겠습니다.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## 결론

Aspose.Words for Java의 구조화된 문서 태그는 문서 내의 콘텐츠를 관리하고 형식을 지정하는 다양한 방법을 제공합니다. 템플릿, 양식 또는 동적 문서를 작성해야 하는 경우 SDT는 필요한 유연성과 제어 기능을 제공합니다. 이 문서에 제공된 예제와 지침을 따르면 SDT의 강력한 기능을 활용하여 문서 처리 작업을 향상할 수 있습니다.

## FAQ

### 구조화된 문서 태그(SDT)의 목적은 무엇입니까?

구조화된 문서 태그(SDT)는 문서 내의 콘텐츠를 구성하고 서식을 지정하는 목적으로 사용되므로 템플릿, 양식 및 구조화된 문서를 더 쉽게 만들 수 있습니다.

### Checkbox SDT의 현재 상태를 어떻게 확인할 수 있나요?

 다음을 사용하여 Checkbox SDT의 현재 상태를 확인할 수 있습니다.`setChecked` 방법은 기사에 나와 있는 대로입니다.

### 콘텐츠 컨트롤에 스타일을 적용할 수 있나요?

예, 콘텐츠 컨트롤에 스타일을 적용하여 문서의 모양을 사용자 지정할 수 있습니다.

### SDT를 사용자 정의 XML 데이터에 바인딩할 수 있습니까?

예, SDT를 사용자 정의 XML 데이터에 바인딩하여 동적 콘텐츠 생성 및 데이터 매핑을 허용할 수 있습니다.

### SDT의 반복 섹션이란 무엇입니까?

SDT의 반복 섹션을 사용하면 매핑된 XML 데이터를 기반으로 행이 반복될 수 있는 동적 데이터가 포함된 테이블을 생성할 수 있습니다.