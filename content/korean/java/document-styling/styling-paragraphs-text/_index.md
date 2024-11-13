---
title: 문서의 문단 및 텍스트 스타일링
linktitle: 문서의 문단 및 텍스트 스타일링
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 문서의 문단과 텍스트에 스타일을 지정하는 방법을 알아보세요. 효과적인 문서 서식을 위한 소스 코드가 포함된 단계별 가이드.
type: docs
weight: 11
url: /ko/java/document-styling/styling-paragraphs-text/
---
## 소개

Java에서 문서를 프로그래밍 방식으로 조작하고 서식을 지정하는 경우 Aspose.Words for Java는 개발자에게 최고의 선택입니다. 이 강력한 API를 사용하면 문서의 문단과 텍스트를 쉽게 만들고, 편집하고, 스타일을 지정할 수 있습니다. 이 포괄적인 가이드에서는 Aspose.Words for Java를 사용하여 문단과 텍스트의 스타일을 지정하는 프로세스를 안내합니다. 노련한 개발자이든 방금 시작한 개발자이든 소스 코드가 포함된 이 단계별 가이드는 문서 서식을 마스터하는 데 필요한 지식과 기술을 제공합니다. 시작해 볼까요!

## Java용 Aspose.Words 이해

Aspose.Words for Java는 개발자가 Microsoft Word 없이도 Word 문서로 작업할 수 있도록 해주는 Java 라이브러리입니다. 문서 생성, 조작 및 서식 지정을 위한 광범위한 기능을 제공합니다. Aspose.Words for Java를 사용하면 보고서, 송장, 계약서 등의 생성을 자동화할 수 있어 기업과 개발자에게 매우 귀중한 도구입니다.

## 개발 환경 설정

코딩 측면을 살펴보기 전에 개발 환경을 설정하는 것이 중요합니다. Java가 설치되어 있는지 확인한 다음 Aspose.Words for Java 라이브러리를 다운로드하여 구성합니다. 자세한 설치 지침은 다음에서 찾을 수 있습니다.[선적 서류 비치](https://reference.aspose.com/words/java/).

## 새 문서 만들기

Aspose.Words for Java를 사용하여 새 문서를 만드는 것으로 시작해 보겠습니다. 아래는 시작하기 위한 간단한 코드 조각입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문서를 저장하세요
doc.save("NewDocument.docx");
```

이 코드는 빈 Word 문서를 생성하여 "NewDocument.docx"로 저장합니다. 콘텐츠와 서식을 추가하여 문서를 더욱 사용자 지정할 수 있습니다.

## 문단 추가 및 서식 지정

문단은 모든 문서의 구성 요소입니다. 필요에 따라 문단을 추가하고 서식을 지정할 수 있습니다. 다음은 문단을 추가하고 정렬을 설정하는 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문단을 만드세요
Paragraph para = new Paragraph(doc);

// 문단의 정렬을 설정합니다
para.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);

// 문단에 텍스트 추가
Run run = new Run(doc, "This is a centered paragraph.");
para.appendChild(run);

// 문서에 문단을 추가합니다
doc.getFirstSection().getBody().appendChild(para);

// 문서를 저장하세요
doc.save("FormattedDocument.docx");
```

이 코드 조각은 "이것은 중앙 단락입니다."라는 텍스트가 있는 중앙 단락을 만듭니다. 원하는 서식을 얻기 위해 글꼴, 색상 등을 사용자 지정할 수 있습니다.

## 문단 내 텍스트 스타일링

문단 내의 개별 텍스트를 포맷하는 것은 일반적인 요구 사항입니다. Aspose.Words for Java를 사용하면 텍스트 스타일을 쉽게 지정할 수 있습니다. 다음은 텍스트의 글꼴과 색상을 변경하는 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문단을 만드세요
Paragraph para = new Paragraph(doc);

// 다양한 서식으로 텍스트 추가
Run run = new Run(doc, "This is ");
run.getFont().setName("Arial");
run.getFont().setSize(14);
para.appendChild(run);

Run coloredRun = new Run(doc, "colored text.");
coloredRun.getFont().setColor(Color.RED);
para.appendChild(coloredRun);

// 문서에 문단을 추가합니다
doc.getFirstSection().getBody().appendChild(para);

// 문서를 저장하세요
doc.save("StyledTextDocument.docx");
```

이 예제에서는 텍스트가 있는 문단을 만든 다음 글꼴과 색상을 변경하여 텍스트의 일부 스타일을 다르게 지정합니다.

## 스타일 및 서식 적용

Aspose.Words for Java는 문단과 텍스트에 적용할 수 있는 미리 정의된 스타일을 제공합니다. 이를 통해 서식 지정 프로세스가 간소화됩니다. 문단에 스타일을 적용하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문단을 만드세요
Paragraph para = new Paragraph(doc);

// 미리 정의된 스타일 적용
para.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);

// 문단에 텍스트 추가
Run run = new Run(doc, "Heading 1 Style");
para.appendChild(run);

// 문서에 문단을 추가합니다
doc.getFirstSection().getBody().appendChild(para);

// 문서를 저장하세요
doc.save("StyledDocument.docx");
```

이 코드에서는 "제목 1" 스타일을 문단에 적용하여 미리 정의된 스타일에 따라 자동으로 서식을 지정합니다.

## 글꼴 및 색상 작업

텍스트의 모양을 미세 조정하는 데는 종종 글꼴과 색상을 수정하는 것이 포함됩니다. Aspose.Words for Java는 글꼴 및 색상 관리에 대한 광범위한 옵션을 제공합니다. 다음은 글꼴 크기와 색상을 변경하는 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문단을 만드세요
Paragraph para = new Paragraph(doc);

// 사용자 정의 글꼴 크기와 색상으로 텍스트 추가
Run run = new Run(doc, "Customized Text");
run.getFont().setSize(18); // 글꼴 크기를 18포인트로 설정하세요
run.getFont().setColor(Color.BLUE); // 텍스트 색상을 파란색으로 설정

para.appendChild(run);

// 문서에 문단을 추가합니다
doc.getFirstSection().getBody().appendChild(para);

// 문서를 저장하세요
doc.save("FontAndColorDocument.docx");
```

이 코드에서는 문단 내 텍스트의 글꼴 크기와 색상을 사용자 지정합니다.

## 정렬 및 간격 관리

문단과 텍스트의 정렬과 간격을 제어하는 것은 문서 레이아웃에 필수적입니다. 정렬과 간격을 조정하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문단을 만드세요
Paragraph para = new Paragraph(doc);

// 문단 정렬 설정
para.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);

// 간격을 두고 텍스트 추가
Run run = new Run(doc, "Right-aligned text with spacing.");
para.appendChild(run);

// 문단 앞뒤에 공백을 추가합니다.
para.getParagraphFormat().setSpaceBefore(10); // 10점 전
para.getParagraphFormat().setSpaceAfter(10);  // 10 포인트 후

// 문서에 문단을 추가합니다
doc.getFirstSection().getBody().appendChild(para);

// 문서를 저장하세요
doc.save("AlignmentAndSpacingDocument.docx");
```

이 예에서 우리는 문단의 정렬을 다음과 같이 설정했습니다.

 오른쪽 정렬하고 문단 앞뒤에 공백을 추가합니다.

## 목록 및 글머리 기호 처리

글머리 기호나 번호 매기기가 있는 목록을 만드는 것은 일반적인 문서 서식 작업입니다. Aspose.Words for Java는 이를 간단하게 만듭니다. 글머리 기호 목록을 만드는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 목록을 만드세요
List list = new List(doc);

// 글머리 기호가 있는 목록 항목 추가
list.getListFormat().setListType(ListTemplateType.BULLET_DEFAULT);
list.getListFormat().setListLevelNumber(0);

list.appendChild(new ListItem(doc, "Item 1"));
list.appendChild(new ListItem(doc, "Item 2"));
list.appendChild(new ListItem(doc, "Item 3"));

// 문서에 목록 추가
doc.getFirstSection().getBody().appendChild(list);

// 문서를 저장하세요
doc.save("BulletedListDocument.docx");
```

이 코드에서는 세 개의 항목으로 구성된 글머리 기호 목록을 만듭니다.

## 하이퍼링크 삽입

하이퍼링크는 문서에 상호 작용을 추가하는 데 필수적입니다. Aspose.Words for Java를 사용하면 하이퍼링크를 쉽게 삽입할 수 있습니다. 다음은 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문단을 만드세요
Paragraph para = new Paragraph(doc);

// 하이퍼링크 만들기
Hyperlink link = new Hyperlink(doc);
link.setAddress("https://www.example.com");
link.appendChild(new Run(doc, "Visit Example.com"));

para.appendChild(link);

// 문서에 문단을 추가합니다
doc.getFirstSection().getBody().appendChild(para);

// 문서를 저장하세요
doc.save("HyperlinkDocument.docx");
```

이 코드는 "Visit Example.com"이라는 텍스트와 함께 "https://www.example.com"에 대한 하이퍼링크를 삽입합니다.

## 이미지 및 모양 추가

문서에는 종종 이미지와 모양과 같은 시각적 요소가 필요합니다. Aspose.Words for Java를 사용하면 이미지와 모양을 원활하게 삽입할 수 있습니다. 이미지를 추가하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문단을 만드세요
Paragraph para = new Paragraph(doc);

// 파일에서 이미지 로드
Shape image = new Shape(doc, ShapeType.IMAGE);
image.getImageData().setImage("path/to/your/image.png");

para.appendChild(image);

// 문서에 문단을 추가합니다
doc.getFirstSection().getBody().appendChild(para);

// 문서를 저장하세요
doc.save("ImageDocument.docx");
```

이 코드에서는 파일에서 이미지를 로드하여 문서에 삽입합니다.

## 페이지 레이아웃 및 여백

원하는 모양을 얻으려면 문서의 페이지 레이아웃과 여백을 제어하는 것이 중요합니다. 페이지 여백을 설정하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 페이지 여백 설정(포인트)
PageSetup pageSetup = doc.getFirstSection().getPageSetup();
pageSetup.setLeftMargin(72);   // 1인치(72포인트)
pageSetup.setRightMargin(72);  // 1인치(72포인트)
pageSetup.setTopMargin(72);    // 1인치(72포인트)
pageSetup.setBottomMargin(72); // 1인치(72포인트)

// 문서에 내용 추가
// ...

// 문서를 저장하세요
doc.save("PageLayoutDocument.docx");
```

이 예에서 우리는 페이지의 모든 면에 1인치의 동일한 여백을 설정했습니다.

## 헤더와 푸터

머리글과 바닥글은 문서의 각 페이지에 일관된 정보를 추가하는 데 필수적입니다. 머리글과 바닥글을 사용하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 첫 번째 섹션의 헤더와 푸터에 접근합니다.
HeaderFooter header = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_PRIMARY);
HeaderFooter footer = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// 헤더에 콘텐츠 추가
Run headerRun = new Run(doc, "Header Text");
header.appendChild(headerRun);

// 푸터에 콘텐츠 추가
Run footerRun = new Run(doc, "Page Number: ");
footer.appendChild(footerRun);
Field pageField = new Field(doc, FieldType.FIELD_PAGE);
footer.appendChild(pageField);

// 문서 본문에 내용 추가
// ...

// 문서를 저장하세요
doc.save("HeaderFooterDocument.docx");
```

이 코드에서는 문서의 머리글과 바닥글에 모두 내용을 추가합니다.

## 테이블 작업

표는 문서에서 데이터를 구성하고 표현하는 강력한 방법입니다. Aspose.Words for Java는 표 작업에 대한 광범위한 지원을 제공합니다. 다음은 표를 만드는 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 3행 3열의 표 만들기
Table table = new Table(doc);
table.ensureMinimum();
table.getRows().add(new Row(doc));
table.getRows().add(new Row(doc));
table.getRows().add(new Row(doc));

// 테이블 셀에 내용 추가
table.getFirstRow().getCells().get(0).appendChild(new Paragraph(doc, "Row 1, Cell 1"));
table.getFirstRow().getCells().get(1).appendChild(new Paragraph(doc, "Row 1, Cell 2"));
table.getFirstRow().getCells().get(2).appendChild(new Paragraph(doc, "Row 1, Cell 3"));

//문서에 표 추가
doc.getFirstSection().getBody().appendChild(table);

// 문서를 저장하세요
doc.save("TableDocument.docx");
```

이 코드에서는 3개의 행과 3개의 열로 구성된 간단한 표를 만듭니다.

## 문서 저장 및 내보내기

문서를 만들고 포맷한 후에는 원하는 형식으로 저장하거나 내보내는 것이 필수적입니다. Aspose.Words for Java는 DOCX, PDF 등 다양한 문서 형식을 지원합니다. 문서를 PDF로 저장하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문서에 내용 추가
// ...

// 문서를 PDF로 저장
doc.save("Document.pdf", SaveFormat.PDF);
```

이 코드 조각은 문서를 PDF 파일로 저장합니다.

## 고급 기능

Aspose.Words for Java는 복잡한 문서 조작을 위한 고급 기능을 제공합니다. 여기에는 메일 병합, 문서 비교 등이 포함됩니다. 이러한 고급 주제에 대한 심층적인 지침은 설명서를 살펴보세요.

## 팁과 모범 사례

- 유지관리가 더 쉬워지도록 코드를 모듈화하고 잘 정리하세요.
- 주석을 사용하면 복잡한 논리를 설명하고 코드의 가독성을 향상시킬 수 있습니다.
- 업데이트 및 추가 리소스를 보려면 Aspose.Words for Java 문서를 정기적으로 참조하세요.

## 일반적인 문제 해결

Aspose.Words for Java에서 작업하는 동안 문제가 발생했습니까? 일반적인 문제에 대한 해결책은 지원 포럼과 문서를 확인하세요.

## 자주 묻는 질문(FAQ)

### 문서에 페이지 나누기를 추가하려면 어떻게 해야 하나요?
문서에 페이지 나누기를 추가하려면 다음 코드를 사용하면 됩니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 페이지 나누기 삽입
builder.insertBreak(BreakType.PAGE_BREAK);

// 문서에 계속해서 내용을 추가합니다.
```

### Aspose.Words for Java를 사용하여 문서를 PDF로 변환할 수 있나요?
네, Aspose.Words for Java를 사용하여 문서를 PDF로 쉽게 변환할 수 있습니다. 다음은 예입니다.

```java
Document doc = new Document("input.docx");
doc.save("output.pdf", SaveFormat.PDF);
```

### 텍스트를 어떻게 포맷합니까?

 굵게 또는 기울임체?
텍스트를 굵게 또는 기울임꼴로 서식 지정하려면 다음 코드를 사용하면 됩니다.

```java
Run run = new Run(doc, "Bold and Italic Text");
run.getFont().setBold(true);    // 텍스트를 굵게 표시
run.getFont().setItalic(true);  // 텍스트를 기울임체로 만들기
```

### Aspose.Words for Java의 최신 버전은 무엇입니까?
Java용 Aspose.Words의 최신 버전은 Aspose 웹사이트나 Maven 저장소에서 확인할 수 있습니다.

### Java용 Aspose.Words는 Java 11과 호환됩니까?
네, Aspose.Words for Java는 Java 11 이상 버전과 호환됩니다.

### 문서의 특정 섹션에 대한 페이지 여백을 어떻게 설정할 수 있나요?
문서의 특정 섹션에 대한 페이지 여백을 설정할 수 있습니다.`PageSetup` 클래스. 다음은 예입니다.

```java
Section section = doc.getSections().get(0); // 첫 번째 섹션을 받으세요
PageSetup pageSetup = section.getPageSetup();
pageSetup.setLeftMargin(72);   // 왼쪽 여백 (포인트)
pageSetup.setRightMargin(72);  // 오른쪽 여백 (포인트)
pageSetup.setTopMargin(72);    // 포인트 단위의 상위 마진
pageSetup.setBottomMargin(72); // 하단 여백 (포인트)
```

## 결론

이 포괄적인 가이드에서는 Aspose.Words for Java의 강력한 기능을 살펴보았습니다. 문서의 단락과 텍스트에 스타일을 적용합니다. 기본 텍스트 조작에서 고급 기능에 이르기까지 문서를 프로그래밍 방식으로 만들고, 서식을 지정하고, 개선하는 방법을 배웠습니다. Aspose.Words for Java는 개발자가 문서 서식 지정 작업을 효율적으로 자동화할 수 있도록 지원합니다. 다양한 기능을 연습하고 실험하여 Aspose.Words for Java로 문서 스타일을 적용하는 데 능숙해지세요.

이제 Aspose.Words for Java를 사용하여 문서의 문단과 텍스트를 스타일링하는 방법을 확실히 이해했으므로 특정 요구 사항에 맞게 조정된 아름답게 포맷된 문서를 만들 준비가 되었습니다. 즐거운 코딩 되세요!