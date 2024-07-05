---
title: 문서의 단락 및 텍스트 스타일 지정
linktitle: 문서의 단락 및 텍스트 스타일 지정
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 문서의 단락과 텍스트 스타일을 지정하는 방법을 알아보세요. 효과적인 문서 서식을 위한 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 11
url: /ko/java/document-styling/styling-paragraphs-text/
---
## 소개

Java에서 프로그래밍 방식으로 문서를 조작하고 서식을 지정하는 경우 Aspose.Words for Java는 개발자들 사이에서 최고의 선택입니다. 이 강력한 API를 사용하면 문서에서 단락과 텍스트를 쉽게 만들고, 편집하고, 스타일을 지정할 수 있습니다. 이 종합 가이드에서는 Aspose.Words for Java를 사용하여 단락과 텍스트의 스타일을 지정하는 과정을 안내합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든, 소스 코드가 포함된 이 단계별 가이드를 통해 문서 형식을 마스터하는 데 필요한 지식과 기술을 얻을 수 있습니다. 뛰어들어보자!

## Java용 Aspose.Words 이해

Aspose.Words for Java는 개발자가 Microsoft Word 없이도 Word 문서로 작업할 수 있도록 하는 Java 라이브러리입니다. 문서 작성, 조작 및 서식 지정을 위한 광범위한 기능을 제공합니다. Aspose.Words for Java를 사용하면 보고서, 송장, 계약서 등의 생성을 자동화하여 기업과 개발자에게 귀중한 도구로 만들 수 있습니다.

## 개발 환경 설정

코딩 측면을 살펴보기 전에 개발 환경을 설정하는 것이 중요합니다. Java가 설치되어 있는지 확인한 다음 Aspose.Words for Java 라이브러리를 다운로드하고 구성하세요. 자세한 설치 지침은 다음에서 확인할 수 있습니다.[선적 서류 비치](https://reference.aspose.com/words/java/).

## 새 문서 만들기

Aspose.Words for Java를 사용하여 새 문서를 만드는 것부터 시작해 보겠습니다. 다음은 시작하는 데 도움이 되는 간단한 코드 조각입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문서 저장
doc.save("NewDocument.docx");
```

이 코드는 빈 Word 문서를 만들고 "NewDocument.docx"로 저장합니다. 콘텐츠와 서식을 추가하여 문서를 추가로 사용자 정의할 수 있습니다.

## 단락 추가 및 서식 지정

단락은 모든 문서의 구성 요소입니다. 필요에 따라 단락을 추가하고 서식을 지정할 수 있습니다. 다음은 단락을 추가하고 정렬을 설정하는 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 단락 만들기
Paragraph para = new Paragraph(doc);

// 단락 정렬 설정
para.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);

// 단락에 텍스트 추가
Run run = new Run(doc, "This is a centered paragraph.");
para.appendChild(run);

// 문서에 단락 추가
doc.getFirstSection().getBody().appendChild(para);

// 문서 저장
doc.save("FormattedDocument.docx");
```

이 코드 조각은 "이것은 가운데 맞춤 단락입니다."라는 텍스트가 포함된 가운데 맞춤 단락을 만듭니다. 글꼴, 색상 등을 사용자 정의하여 원하는 형식을 얻을 수 있습니다.

## 단락 내의 텍스트 스타일 지정

단락 내의 개별 텍스트 서식을 지정하는 것은 일반적인 요구 사항입니다. Aspose.Words for Java를 사용하면 텍스트 스타일을 쉽게 지정할 수 있습니다. 다음은 텍스트의 글꼴과 색상을 변경하는 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 단락 만들기
Paragraph para = new Paragraph(doc);

// 다른 서식으로 텍스트 추가
Run run = new Run(doc, "This is ");
run.getFont().setName("Arial");
run.getFont().setSize(14);
para.appendChild(run);

Run coloredRun = new Run(doc, "colored text.");
coloredRun.getFont().setColor(Color.RED);
para.appendChild(coloredRun);

// 문서에 단락 추가
doc.getFirstSection().getBody().appendChild(para);

// 문서 저장
doc.save("StyledTextDocument.docx");
```

이 예에서는 텍스트가 포함된 단락을 만든 다음 글꼴과 색상을 변경하여 텍스트 부분의 스타일을 다르게 지정합니다.

## 스타일 및 서식 적용

Aspose.Words for Java는 단락과 텍스트에 적용할 수 있는 미리 정의된 스타일을 제공합니다. 이렇게 하면 포맷 프로세스가 단순화됩니다. 단락에 스타일을 적용하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 단락 만들기
Paragraph para = new Paragraph(doc);

// 미리 정의된 스타일 적용
para.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);

// 단락에 텍스트 추가
Run run = new Run(doc, "Heading 1 Style");
para.appendChild(run);

// 문서에 단락 추가
doc.getFirstSection().getBody().appendChild(para);

// 문서 저장
doc.save("StyledDocument.docx");
```

이 코드에서는 미리 정의된 스타일에 따라 자동으로 서식을 지정하는 "제목 1" 스타일을 단락에 적용합니다.

## 글꼴 및 색상 작업

텍스트 모양을 미세 조정하려면 글꼴과 색상을 수정해야 하는 경우가 많습니다. Aspose.Words for Java는 글꼴 및 색상 관리를 위한 광범위한 옵션을 제공합니다. 다음은 글꼴 크기와 색상을 변경하는 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 단락 만들기
Paragraph para = new Paragraph(doc);

// 사용자 정의 글꼴 크기 및 색상으로 텍스트 추가
Run run = new Run(doc, "Customized Text");
run.getFont().setSize(18); // 글꼴 크기를 18포인트로 설정
run.getFont().setColor(Color.BLUE); // 텍스트 색상을 파란색으로 설정

para.appendChild(run);

// 문서에 단락 추가
doc.getFirstSection().getBody().appendChild(para);

// 문서 저장
doc.save("FontAndColorDocument.docx");
```

이 코드에서는 단락 내 텍스트의 글꼴 크기와 색상을 사용자 정의합니다.

## 정렬 및 간격 관리

단락과 텍스트의 정렬과 간격을 제어하는 것은 문서 레이아웃에 필수적입니다. 정렬과 간격을 조정하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 단락 만들기
Paragraph para = new Paragraph(doc);

// 단락 정렬 설정
para.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);

// 간격을 두고 텍스트 추가
Run run = new Run(doc, "Right-aligned text with spacing.");
para.appendChild(run);

// 단락 앞뒤에 간격 추가
para.getParagraphFormat().setSpaceBefore(10); // 10점 전
para.getParagraphFormat().setSpaceAfter(10);  // 10점 이후

// 문서에 단락 추가
doc.getFirstSection().getBody().appendChild(para);

// 문서 저장
doc.save("AlignmentAndSpacingDocument.docx");
```

이 예에서는 단락 정렬을 다음과 같이 설정합니다.

 오른쪽 정렬하고 단락 앞과 뒤에 간격을 추가합니다.

## 목록 및 글머리 기호 처리

글머리 기호 또는 번호 매기기를 사용하여 목록을 만드는 것은 일반적인 문서 서식 지정 작업입니다. Aspose.Words for Java는 이를 간단하게 만듭니다. 글머리 기호 목록을 만드는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 목록 만들기
List list = new List(doc);

// 글머리 기호가 있는 목록 항목 추가
list.getListFormat().setListType(ListTemplateType.BULLET_DEFAULT);
list.getListFormat().setListLevelNumber(0);

list.appendChild(new ListItem(doc, "Item 1"));
list.appendChild(new ListItem(doc, "Item 2"));
list.appendChild(new ListItem(doc, "Item 3"));

// 문서에 목록 추가
doc.getFirstSection().getBody().appendChild(list);

// 문서 저장
doc.save("BulletedListDocument.docx");
```

이 코드에서는 세 가지 항목이 포함된 글머리 기호 목록을 만듭니다.

## 하이퍼링크 삽입

문서에 대화형 기능을 추가하려면 하이퍼링크가 필수적입니다. Aspose.Words for Java를 사용하면 하이퍼링크를 쉽게 삽입할 수 있습니다. 예는 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 단락 만들기
Paragraph para = new Paragraph(doc);

// 하이퍼링크 만들기
Hyperlink link = new Hyperlink(doc);
link.setAddress("https://www.example.com");
link.appendChild(new Run(doc, "Visit Example.com"));

para.appendChild(link);

// 문서에 단락 추가
doc.getFirstSection().getBody().appendChild(para);

// 문서 저장
doc.save("HyperlinkDocument.docx");
```

이 코드는 "Visit example.com"이라는 텍스트와 함께 "https://www.example.com"에 대한 하이퍼링크를 삽입합니다.

## 이미지 및 도형 추가

문서에는 이미지나 도형과 같은 시각적 요소가 필요한 경우가 많습니다. Aspose.Words for Java를 사용하면 이미지와 모양을 원활하게 삽입할 수 있습니다. 이미지를 추가하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 단락 만들기
Paragraph para = new Paragraph(doc);

// 파일에서 이미지 로드
Shape image = new Shape(doc, ShapeType.IMAGE);
image.getImageData().setImage("path/to/your/image.png");

para.appendChild(image);

// 문서에 단락 추가
doc.getFirstSection().getBody().appendChild(para);

// 문서 저장
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

// 문서에 콘텐츠 추가
// ...

// 문서 저장
doc.save("PageLayoutDocument.docx");
```

이 예에서는 페이지의 모든 측면에 1인치의 동일한 여백을 설정했습니다.

## 머리글과 바닥 글

머리글과 바닥글은 문서의 각 페이지에 일관된 정보를 추가하는 데 필수적입니다. 머리글과 바닥글을 사용하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 첫 번째 섹션의 머리글 및 바닥글에 액세스
HeaderFooter header = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_PRIMARY);
HeaderFooter footer = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// 헤더에 콘텐츠 추가
Run headerRun = new Run(doc, "Header Text");
header.appendChild(headerRun);

// 바닥글에 콘텐츠 추가
Run footerRun = new Run(doc, "Page Number: ");
footer.appendChild(footerRun);
Field pageField = new Field(doc, FieldType.FIELD_PAGE);
footer.appendChild(pageField);

// 문서 본문에 내용 추가
// ...

// 문서 저장
doc.save("HeaderFooterDocument.docx");
```

이 코드에서는 문서의 머리글과 바닥글 모두에 콘텐츠를 추가합니다.

## 테이블 작업

표는 문서의 데이터를 구성하고 표시하는 강력한 방법입니다. Aspose.Words for Java는 테이블 작업에 대한 광범위한 지원을 제공합니다. 다음은 테이블을 생성하는 예입니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 행 3개와 열 3개로 구성된 테이블 만들기
Table table = new Table(doc);
table.ensureMinimum();
table.getRows().add(new Row(doc));
table.getRows().add(new Row(doc));
table.getRows().add(new Row(doc));

// 표 셀에 내용 추가
table.getFirstRow().getCells().get(0).appendChild(new Paragraph(doc, "Row 1, Cell 1"));
table.getFirstRow().getCells().get(1).appendChild(new Paragraph(doc, "Row 1, Cell 2"));
table.getFirstRow().getCells().get(2).appendChild(new Paragraph(doc, "Row 1, Cell 3"));

//문서에 표 추가
doc.getFirstSection().getBody().appendChild(table);

// 문서 저장
doc.save("TableDocument.docx");
```

이 코드에서는 3개의 행과 3개의 열이 있는 간단한 테이블을 만듭니다.

## 문서 저장 및 내보내기

문서를 만들고 서식을 지정한 후에는 원하는 형식으로 저장하거나 내보내는 것이 중요합니다. Aspose.Words for Java는 DOCX, PDF 등을 포함한 다양한 문서 형식을 지원합니다. 문서를 PDF로 저장하는 방법은 다음과 같습니다.

```java
// 새 문서 만들기
Document doc = new Document();

// 문서에 콘텐츠 추가
// ...

// 문서를 PDF로 저장
doc.save("Document.pdf", SaveFormat.PDF);
```

이 코드 조각은 문서를 PDF 파일로 저장합니다.

## 고급 기능

Aspose.Words for Java는 복잡한 문서 조작을 위한 고급 기능을 제공합니다. 여기에는 메일 병합, 문서 비교 등이 포함됩니다. 이러한 고급 주제에 대한 심층적인 지침을 보려면 설명서를 살펴보세요.

## 팁과 모범 사례

- 더 쉬운 유지 관리를 위해 코드를 모듈화하고 체계적으로 구성하세요.
- 주석을 사용하여 복잡한 논리를 설명하고 코드 가독성을 높입니다.
- 업데이트 및 추가 리소스에 대해서는 Java용 Aspose.Words 문서를 정기적으로 참조하세요.

## 일반적인 문제 해결

Aspose.Words for Java로 작업하는 동안 문제가 발생합니까? 일반적인 문제에 대한 해결 방법은 지원 포럼 및 설명서를 확인하세요.

## 자주 묻는 질문(FAQ)

### 내 문서에 페이지 나누기를 어떻게 추가하나요?
문서에 페이지 나누기를 추가하려면 다음 코드를 사용할 수 있습니다.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 페이지 나누기 삽입
builder.insertBreak(BreakType.PAGE_BREAK);

// 계속해서 문서에 콘텐츠를 추가하세요.
```

### Aspose.Words for Java를 사용하여 문서를 PDF로 변환할 수 있나요?
예, Aspose.Words for Java를 사용하면 문서를 PDF로 쉽게 변환할 수 있습니다. 예는 다음과 같습니다.

```java
Document doc = new Document("input.docx");
doc.save("output.pdf", SaveFormat.PDF);
```

### 텍스트 서식을 어떻게 지정합니까?

 굵게 또는 이탤릭체로?
텍스트의 서식을 굵게 또는 기울임꼴로 지정하려면 다음 코드를 사용할 수 있습니다.

```java
Run run = new Run(doc, "Bold and Italic Text");
run.getFont().setBold(true);    // 텍스트를 굵게 표시
run.getFont().setItalic(true);  // 텍스트를 이탤릭체로 만들기
```

### Java용 Aspose.Words의 최신 버전은 무엇입니까?
Aspose 웹사이트나 Maven 저장소에서 최신 버전의 Aspose.Words for Java를 확인할 수 있습니다.

### Aspose.Words for Java는 Java 11과 호환됩니까?
예, Aspose.Words for Java는 Java 11 이상 버전과 호환됩니다.

### 내 문서의 특정 섹션에 대해 페이지 여백을 어떻게 설정합니까?
다음을 사용하여 문서의 특정 섹션에 대한 페이지 여백을 설정할 수 있습니다.`PageSetup` 수업. 예는 다음과 같습니다.

```java
Section section = doc.getSections().get(0); // 첫 번째 섹션 가져오기
PageSetup pageSetup = section.getPageSetup();
pageSetup.setLeftMargin(72);   // 왼쪽 여백(포인트)
pageSetup.setRightMargin(72);  // 오른쪽 여백(포인트)
pageSetup.setTopMargin(72);    // 최고 마진(포인트)
pageSetup.setBottomMargin(72); // 하단 여백(포인트)
```

## 결론

이 포괄적인 가이드에서 우리는 문서의 단락과 텍스트 스타일을 지정하기 위한 Aspose.Words for Java의 강력한 기능을 살펴보았습니다. 기본 텍스트 조작부터 고급 기능까지 프로그래밍 방식으로 문서를 생성하고 형식을 지정하고 개선하는 방법을 배웠습니다. Aspose.Words for Java는 개발자가 문서 서식 지정 작업을 효율적으로 자동화할 수 있도록 지원합니다. Aspose.Words for Java를 사용하여 문서 스타일링에 능숙해지기 위해 다양한 기능을 계속 연습하고 실험하세요.

이제 Aspose.Words for Java를 사용하여 문서에서 단락과 텍스트의 스타일을 지정하는 방법을 확실히 이해했으므로 특정 요구 사항에 맞는 아름다운 형식의 문서를 만들 준비가 되었습니다. 즐거운 코딩하세요!