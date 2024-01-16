---
title: 문서 워터마킹 및 페이지 설정
linktitle: 문서 워터마킹 및 페이지 설정
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 워터마크를 적용하고 페이지 구성을 설정하는 방법을 알아보세요. 소스 코드가 포함된 포괄적인 가이드입니다.
type: docs
weight: 13
url: /ko/java/document-styling/document-watermarking-page-setup/
---
## 소개

문서 조작 영역에서 Aspose.Words for Java는 개발자가 문서 처리의 모든 측면을 제어할 수 있는 강력한 도구입니다. 이 포괄적인 가이드에서는 Aspose.Words for Java를 사용하여 문서 워터마킹 및 페이지 설정의 복잡성을 자세히 살펴보겠습니다. 숙련된 개발자이거나 Java 문서 처리의 세계에 입문한 사람이라면 이 단계별 가이드를 통해 필요한 지식과 소스 코드를 얻을 수 있습니다.

## 문서 워터마킹

### 워터마크 추가

문서에 워터마크를 추가하는 것은 콘텐츠의 브랜딩이나 보안을 위해 매우 중요할 수 있습니다. Aspose.Words for Java는 이 작업을 간단하게 만듭니다. 방법은 다음과 같습니다.

```java
// 문서를 로드하세요
Document doc = new Document("document.docx");

// 워터마크 만들기
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// 워터마크 위치 지정
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// 워터마크 삽입
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// 문서 저장
doc.save("document_with_watermark.docx");
```

### 워터마크 사용자 정의

글꼴, 크기, 색상 및 회전을 조정하여 워터마크를 추가로 사용자 정의할 수 있습니다. 이러한 유연성을 통해 워터마크가 문서 스타일과 완벽하게 일치할 수 있습니다.

## 페이지 설정

### 페이지 크기 및 방향

페이지 설정은 문서 서식에 있어서 매우 중요합니다. Aspose.Words for Java는 페이지 크기와 방향을 완벽하게 제어합니다.

```java
// 문서를 로드하세요
Document doc = new Document("document.docx");

// 페이지 크기를 A4로 설정
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// 페이지 방향을 가로로 변경
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// 수정된 문서를 저장하세요
doc.save("formatted_document.docx");
```

### 여백 및 페이지 번호 매기기

전문적인 문서에서는 여백과 페이지 번호 매기기를 정밀하게 제어하는 것이 필수적입니다. Aspose.Words for Java를 사용하면 다음과 같은 목표를 달성할 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("document.docx");

// 여백 설정
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// 페이지 번호 매기기 활성화
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// 서식이 지정된 문서를 저장하세요.
doc.save("formatted_document.docx");
```

## 자주 묻는 질문

### 문서에서 워터마크를 제거하려면 어떻게 해야 합니까?

문서에서 워터마크를 제거하려면 문서의 모양을 반복하여 워터마크를 나타내는 모양을 제거하면 됩니다. 다음은 일부 내용입니다.

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### 단일 문서에 여러 개의 워터마크를 추가할 수 있나요?

예, 추가 모양 개체를 만들고 필요에 따라 위치를 지정하여 문서에 여러 워터마크를 추가할 수 있습니다.

### 가로 방향에서 페이지 크기를 Legal로 어떻게 변경합니까?

가로 방향에서 페이지 크기를 Legal로 설정하려면 다음과 같이 페이지 너비와 높이를 수정하십시오.

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### 워터마크의 기본 글꼴은 무엇입니까?

워터마크의 기본 글꼴은 글꼴 크기가 36인 Calibri입니다.

### 특정 페이지부터 시작하는 페이지 번호를 어떻게 추가하나요?

문서의 시작 페이지 번호를 다음과 같이 설정하면 됩니다.

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### 머리글이나 바닥글의 텍스트를 가운데 정렬하려면 어떻게 해야 합니까?

머리글이나 바닥글 내의 Paragraph 개체에 대해 setAlignment 메서드를 사용하여 머리글이나 바닥글의 텍스트를 가운데 정렬할 수 있습니다.

## 결론

이 광범위한 가이드에서 우리는 Aspose.Words for Java를 사용하여 문서 워터마킹 및 페이지 설정 기술을 살펴보았습니다. 제공된 소스 코드 조각과 통찰력을 바탕으로 이제 문서를 정교하게 조작하고 서식을 지정할 수 있는 도구를 갖게 되었습니다. Aspose.Words for Java를 사용하면 정확한 사양에 맞는 전문적인 브랜드 문서를 만들 수 있습니다.

문서 조작을 마스터하는 것은 개발자에게 귀중한 기술이며 Aspose.Words for Java는 이 여정에서 신뢰할 수 있는 동반자입니다. 지금 바로 멋진 문서 작성을 시작해 보세요!