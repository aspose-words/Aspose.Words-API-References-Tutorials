---
title: Aspose.Words for Java에서 머리글과 바닥글 사용하기
linktitle: 머리글 및 바닥글 사용
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java에서 머리글과 바닥글을 사용하는 방법을 단계별로 알아보세요. 전문적인 문서를 손쉽게 작성해 보세요.
type: docs
weight: 16
url: /ko/java/using-document-elements/using-headers-and-footers/
---

이 종합 가이드에서는 Aspose.Words for Java에서 머리글과 바닥글을 사용하는 과정을 안내합니다. 머리글과 바닥글은 문서 서식의 필수 요소이며 Aspose.Words는 필요에 따라 이를 생성하고 사용자 정의할 수 있는 강력한 도구를 제공합니다.

이제 각 단계를 자세히 살펴보겠습니다.

## 1. Aspose.Words 소개

Aspose.Words는 프로그래밍 방식으로 Word 문서를 생성, 조작 및 렌더링할 수 있는 강력한 Java API입니다. 머리글과 바닥글을 포함하여 문서 서식을 위한 광범위한 기능을 제공합니다.

## 2. Java 환경 설정

 Aspose.Words 사용을 시작하기 전에 Java 개발 환경이 올바르게 설정되어 있는지 확인하세요. Aspose.Words 문서 페이지에서 필요한 설정 지침을 찾을 수 있습니다:[Aspose.Words 자바 문서](https://reference.aspose.com/words/java/).

## 3. 새 문서 만들기

머리글과 바닥글을 사용하려면 Aspose.Words를 사용하여 새 문서를 만들어야 합니다. 다음 코드는 이를 수행하는 방법을 보여줍니다.

```java
// 새 문서를 생성하기 위한 Java 코드
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. 페이지 설정 이해

 페이지 설정은 문서 레이아웃을 제어하는 데 중요합니다. 다음을 사용하여 머리글 및 바닥글과 관련된 다양한 속성을 지정할 수 있습니다.`PageSetup` 수업. 예를 들어:

```java
// 페이지 속성 설정
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. 다른 첫 페이지 머리글/바닥글

Aspose.Words를 사용하면 문서의 첫 번째 페이지에 대해 서로 다른 머리글과 바닥글을 가질 수 있습니다. 사용`pageSetup.setDifferentFirstPageHeaderFooter(true);` 이 기능을 활성화하려면

## 6. 헤더 작업

### 6.1. 헤더에 텍스트 추가

 다음을 사용하여 헤더에 텍스트를 추가할 수 있습니다.`DocumentBuilder`. 예는 다음과 같습니다.

```java
// 첫 페이지 머리글에 텍스트 추가
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. 헤더에 이미지 삽입

 헤더에 이미지를 삽입하려면`insertImage` 방법. 예는 다음과 같습니다.

```java
// 헤더에 이미지 삽입
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. 헤더 스타일 사용자 정의

위의 예와 같이 글꼴, 정렬 등과 같은 다양한 속성을 설정하여 헤더 스타일을 사용자 정의할 수 있습니다.

## 7. 바닥글 작업

### 7.1. 바닥글에 텍스트 추가

 머리글과 마찬가지로 다음을 사용하여 바닥글에 텍스트를 추가할 수 있습니다.`DocumentBuilder`. 예는 다음과 같습니다.

```java
// 기본 바닥글에 텍스트 추가
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// 필요에 따라 텍스트 및 필드 삽입
```

### 7.2. 바닥글에 이미지 삽입

 바닥글에 이미지를 삽입하려면`insertImage` 헤더와 마찬가지로 메소드입니다.

### 7.3. 바닥글 스타일 사용자 정의

 다음을 사용하여 바닥글 스타일을 사용자 정의합니다.`DocumentBuilder`헤더 사용자 정의와 유사합니다.

## 8. 페이지 번호 매기기

 다음과 같은 필드를 사용하여 머리글과 바닥글에 페이지 번호를 포함할 수 있습니다.`PAGE`그리고`NUMPAGES`. 페이지를 추가하거나 제거하면 이러한 필드가 자동으로 업데이트됩니다.

## 9. 바닥글의 저작권 정보

문서의 바닥글에 저작권 정보를 추가하려면 코드 조각에 표시된 것처럼 두 개의 셀이 있는 표를 사용하여 하나는 왼쪽으로, 다른 하나는 오른쪽으로 정렬하면 됩니다.

## 10. 여러 섹션 작업

Aspose.Words를 사용하면 문서 내의 여러 섹션으로 작업할 수 있습니다. 각 섹션마다 다른 페이지 설정과 머리글/바닥글을 설정할 수 있습니다.

## 11. 가로 방향

필요한 경우 특정 섹션의 방향을 가로 모드로 변경할 수 있습니다.

## 12. 이전 섹션의 머리글/바닥글 복사하기

복잡한 문서를 만들 때 이전 섹션의 머리글과 바닥글을 복사하면 시간을 절약할 수 있습니다.

## 13. 문서 저장

문서를 만들고 사용자 정의한 후에는 다음을 사용하여 저장하는 것을 잊지 마십시오.`doc.save()` 방법.

## 완전한 소스 코드
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // 첫 번째 페이지의 머리글/바닥글을 다른 페이지와 다르게 할지 지정합니다.
        // PageSetup.OddAndEvenPagesHeaderFooter 속성을 사용하여 지정할 수도 있습니다.
        // 홀수 페이지와 짝수 페이지의 머리글/바닥글이 다릅니다.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // 헤더의 상단/왼쪽 모서리에 위치가 지정된 이미지를 삽입합니다.
        // 페이지 상단/왼쪽 가장자리로부터의 거리는 10포인트로 설정됩니다.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // 두 개의 셀이 있는 표를 사용하여 줄에 있는 텍스트의 한 부분을 만듭니다(페이지 번호 매기기 포함).
        // 왼쪽으로 정렬하고 텍스트의 다른 부분(저작권 포함)을 오른쪽으로 정렬합니다.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // PAGE 및 NUMPAGES 필드를 사용하여 현재 페이지 번호와 많은 페이지를 자동 계산합니다.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // 페이지 나누기를 만들어 기본 머리글/바닥글이 표시되는 두 번째 페이지를 만듭니다.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // 이 섹션에는 다른 첫 페이지 머리글/바닥글이 필요하지 않으며 문서에 제목 페이지 하나만 있으면 됩니다.
        //이 페이지의 머리글/바닥글은 이전 섹션에서 이미 정의되었습니다.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // 이 섹션에는 이전 섹션의 머리글/바닥글이 표시됩니다.
        // 기본적으로 이 페이지 너비를 취소하려면 currentSection.HeadersFooters.LinkToPrevious(false)를 호출하세요.
        // 새 섹션에서는 다르기 때문에 바닥글 테이블에 대해 다른 셀 너비를 설정해야 합니다.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // 이 섹션에 대해 기존 머리글/바닥글 세트를 사용하려는 경우.
        // 그러나 약간의 수정을 가하면 머리글/바닥글을 복사하는 것이 편리할 수 있습니다.
        // 이전 섹션에서 원하는 곳에 필요한 수정 사항을 적용합니다.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
copyHeadersFootersFromPreviousSection 메소드의 소스 코드
```java
    /// <요약>
    /// 머리글/바닥글을 복제하여 이전 섹션을 지정된 섹션으로 복사합니다.
    /// </summary>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## 결론

이 튜토리얼에서는 Aspose.Words for Java의 머리글과 바닥글 작업에 대한 기본 사항을 다루었습니다. 머리글과 바닥글을 만들고, 사용자 정의하고, 스타일을 지정하는 방법과 기타 필수 문서 서식 지정 기술을 배웠습니다.

 자세한 내용과 고급 기능은 다음을 참조하세요.[Aspose.Words 자바 문서](https://reference.aspose.com/words/java/).

## 자주 묻는 질문

### 1. 문서 바닥글에 페이지 번호를 어떻게 추가하나요?
 페이지 번호를 삽입하여 추가할 수 있습니다.`PAGE` Aspose.Words를 사용하여 바닥글에 필드를 추가합니다.

### 2. Aspose.Words는 Java 개발 환경과 호환됩니까?
예, Aspose.Words는 Java 개발을 지원합니다. 필요한 설정이 제대로 되어 있는지 확인하세요.

### 3. 머리글과 바닥글의 글꼴과 스타일을 사용자 지정할 수 있나요?
물론 글꼴, 정렬 및 기타 스타일을 사용자 정의하여 머리글과 바닥글을 시각적으로 매력적으로 만들 수 있습니다.

### 4. 홀수 페이지와 짝수 페이지에 서로 다른 헤더를 가질 수 있나요?
 예, 사용할 수 있습니다`PageSetup.OddAndEvenPagesHeaderFooter` 홀수 페이지와 짝수 페이지에 서로 다른 헤더를 지정합니다.

### 5. Aspose.Words for Java를 시작하려면 어떻게 해야 하나요?
 시작하려면 다음을 방문하세요.[Aspose.Words 자바 문서](https://reference.aspose.com/words/java/) API 사용에 대한 포괄적인 지침을 확인하세요.