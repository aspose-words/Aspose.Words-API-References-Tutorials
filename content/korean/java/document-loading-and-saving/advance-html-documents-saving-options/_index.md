---
title: Aspose.Words Java를 사용한 고급 HTML 문서 저장 옵션
linktitle: HTML 문서 저장
second_title: Aspose.Words Java 문서 처리 API
description: 이 튜토리얼에서는 Aspose.Words for Java를 사용하여 다양한 고급 HTML 문서 저장 옵션을 다루었습니다. 이러한 옵션을 사용하면 고품질 HTML을 만들 수 있습니다.
type: docs
weight: 16
url: /ko/java/document-loading-and-saving/advance-html-documents-saving-options/
---

이 튜토리얼에서는 Aspose.Words for Java가 제공하는 고급 HTML 문서 저장 옵션을 살펴보겠습니다. Aspose.Words는 Word 문서 작업을 위한 강력한 Java API이며 문서 조작 및 변환을 위한 광범위한 기능을 제공합니다.

## 1. 소개
Aspose.Words for Java를 사용하면 Word 문서를 프로그래밍 방식으로 작업할 수 있습니다. 이 튜토리얼에서는 Word 문서를 HTML로 변환하는 방법을 제어할 수 있는 고급 HTML 문서 저장 옵션에 중점을 둘 것입니다.

## 2. 왕복 정보 내보내기
 그만큼`exportRoundtripInformation` 방법을 사용하면 왕복 정보를 유지하면서 Word 문서를 HTML로 내보낼 수 있습니다. 이 정보는 문서별 세부 정보를 잃지 않고 HTML을 다시 Word 형식으로 변환하려는 경우 유용할 수 있습니다.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. 글꼴을 Base64로 내보내기
 와 함께`exportFontsAsBase64` 방법을 사용하면 문서에 사용된 글꼴을 HTML의 Base64 인코딩 데이터로 내보낼 수 있습니다. 이렇게 하면 HTML 표현이 원본 Word 문서와 동일한 글꼴 스타일을 유지하게 됩니다.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. 자원 수출
 그만큼`exportResources` 메서드를 사용하면 CSS 스타일시트 유형을 지정하고 글꼴 리소스를 내보낼 수 있습니다. HTML에서 리소스 폴더와 리소스 별칭을 설정할 수도 있습니다.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. 메타파일을 EMF 또는 WMF로 변환
 그만큼`convertMetafilesToEmfOrWmf`메서드를 사용하면 문서의 메타파일을 EMF 또는 WMF 형식으로 변환하여 HTML에서 호환성과 원활한 렌더링을 보장할 수 있습니다.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // 간결성을 위해 코드 조각은 표시되지 않았습니다.
}
```

## 6. 메타파일을 SVG로 변환
 사용`convertMetafilesToSvg` 메타파일을 SVG 형식으로 변환하는 방법. 이 형식은 HTML 문서에 벡터 그래픽을 표시하는 데 적합합니다.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // 간결성을 위해 코드 조각은 표시되지 않았습니다.
}
```

## 7. CSS 클래스 이름 접두사 추가
 와 함께`addCssClassNamePrefix` 방법을 사용하면 내보낸 HTML의 CSS 클래스 이름에 접두사를 추가할 수 있습니다. 이렇게 하면 기존 스타일과의 충돌을 방지하는 데 도움이 됩니다.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. MHTML 리소스에 대한 CID URL 내보내기
 그만큼`exportCidUrlsForMhtmlResources` MHTML 형식으로 문서를 저장할 때 메소드가 사용됩니다. 리소스에 대한 Content-ID URL을 내보낼 수 있습니다.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // 간결성을 위해 코드 조각은 표시되지 않았습니다.
}
```

## 9. 글꼴 이름 확인
 그만큼`resolveFontNames` 메서드는 문서를 HTML 형식으로 저장할 때 글꼴 이름을 확인하여 다양한 플랫폼에서 일관된 렌더링을 보장합니다.

```java
@Test
public void resolveFontNames() throws Exception {
    // 간결성을 위해 코드 조각은 표시되지 않았습니다.
}
```

## 10. 텍스트 입력 양식 필드를 텍스트로 내보내기
 그만큼`exportTextInputFormFieldAsText` 메소드는 양식 필드를 HTML의 일반 텍스트로 내보내어 쉽게 읽고 편집할 수 있도록 합니다.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // 간결성을 위해 코드 조각은 표시되지 않았습니다.
}
```

## 11. 결론
이 튜토리얼에서는 Aspose.Words for Java가 제공하는 고급 HTML 문서 저장 옵션을 살펴보았습니다. 이러한 옵션을 사용하면 변환 프로세스를 세밀하게 제어할 수 있으므로 원본 Word 문서와 매우 유사한 HTML 문서를 만들 수 있습니다.

## 12. FAQ
다음은 Aspose.Words for Java 및 HTML 문서 저장 옵션 작업에 관해 자주 묻는 질문입니다:

### Q1: Aspose.Words for Java를 사용하여 HTML을 다시 Word 형식으로 변환하려면 어떻게 해야 합니까?
 HTML을 다시 Word 형식으로 변환하려면 Aspose.Words API를 사용할 수 있습니다.`load` HTML 문서를 로드한 다음 Word 형식으로 저장하는 방법입니다.

### Q2: HTML로 내보낼 때 CSS 스타일을 사용자 정의할 수 있습니까?
 예, HTML에 사용된 스타일시트를 수정하거나`addCssClassNamePrefix` CSS 클래스 이름에 접두사를 추가하는 방법입니다.

### Q3: 웹 디스플레이에 맞게 HTML 출력을 최적화할 수 있는 방법이 있습니까?
예, 글꼴을 Base64로 내보내고 메타파일을 SVG로 변환하는 등의 옵션을 구성하여 웹 표시용 HTML 출력을 최적화할 수 있습니다.

### Q4: 복잡한 Word 문서를 HTML로 변환할 때 제한 사항이 있습니까?
Aspose.Words for Java는 강력한 변환 기능을 제공하지만 복잡한 레이아웃이 있는 복잡한 Word 문서는 원하는 HTML 출력을 얻기 위해 추가 후처리가 필요할 수 있습니다.
