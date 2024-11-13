---
title: Aspose.Words for Java에서 문서를 PDF로 저장하기
linktitle: 문서를 PDF로 저장
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 Word 문서를 PDF로 저장하는 방법을 알아보세요. 글꼴, 속성 및 이미지 품질을 사용자 정의하세요. PDF 변환을 위한 포괄적인 가이드.
type: docs
weight: 22
url: /ko/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Aspose.Words for Java에서 문서를 PDF로 저장하는 방법 소개

이 단계별 가이드에서는 Aspose.Words for Java를 사용하여 문서를 PDF로 저장하는 방법을 살펴보겠습니다. PDF 변환의 다양한 측면을 다루고 프로세스를 더 쉽게 만들기 위한 코드 예제를 제공합니다.

## 필수 조건

시작하기 전에 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
-  Aspose.Words for Java 라이브러리입니다. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/java/).

## 문서를 PDF로 변환

Word 문서를 PDF로 변환하려면 다음 코드 조각을 사용할 수 있습니다.

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 바꾸다`"input.docx"` Word 문서로의 경로와 함께`"output.pdf"` 원하는 출력 PDF 파일 경로를 입력합니다.

## PDF 저장 옵션 제어

 다양한 PDF 저장 옵션을 제어할 수 있습니다.`PdfSaveOptions` 클래스. 예를 들어, PDF 문서의 표시 제목을 다음과 같이 설정할 수 있습니다.

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## PDF에 글꼴 포함하기

생성된 PDF에 글꼴을 포함하려면 다음 코드를 사용하세요.

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## 문서 속성 사용자 정의

생성된 PDF에서 문서 속성을 사용자 정의할 수 있습니다. 예:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## 문서 구조 내보내기

 문서 구조를 내보내려면 다음을 설정하세요.`exportDocumentStructure` 옵션`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## 이미지 압축

다음 코드를 사용하여 이미지 압축을 제어할 수 있습니다.

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## 마지막으로 인쇄된 속성 업데이트

PDF에서 "마지막으로 인쇄됨" 속성을 업데이트하려면 다음을 사용하세요.

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## DML 3D 효과 렌더링

DML 3D 효과의 고급 렌더링을 위해 렌더링 모드를 설정하세요:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## 이미지 보간

이미지 보간을 활성화하여 이미지 품질을 개선할 수 있습니다.

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## 결론

Aspose.Words for Java는 유연성과 사용자 정의 옵션을 통해 Word 문서를 PDF 형식으로 변환하는 포괄적인 기능을 제공합니다. 글꼴, 문서 속성, 이미지 압축 등을 포함하여 PDF 출력의 다양한 측면을 제어할 수 있습니다.

## 자주 묻는 질문

### Aspose.Words for Java를 사용하여 Word 문서를 PDF로 변환하려면 어떻게 해야 하나요?

Word 문서를 PDF로 변환하려면 다음 코드를 사용하세요.

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 바꾸다`"input.docx"` Word 문서로의 경로와 함께`"output.pdf"` 원하는 출력 PDF 파일 경로를 입력합니다.

### Aspose.Words for Java로 생성된 PDF에 글꼴을 포함할 수 있나요?

 예, PDF에 글꼴을 포함하려면 다음을 설정하세요.`setEmbedFullFonts` 옵션`true` ~에`PdfSaveOptions`. 다음은 예입니다.

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### 생성된 PDF에서 문서 속성을 사용자 지정하려면 어떻게 해야 하나요?

 PDF에서 문서 속성을 사용자 정의하려면 다음을 사용하십시오.`setCustomPropertiesExport` 옵션으로`PdfSaveOptions`. 예를 들어:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Aspose.Words for Java에서 이미지 압축의 목적은 무엇입니까?

 이미지 압축을 사용하면 생성된 PDF의 이미지 품질과 크기를 제어할 수 있습니다. 다음을 사용하여 이미지 압축 모드를 설정할 수 있습니다.`setImageCompression` ~에`PdfSaveOptions`.

### PDF에서 "마지막 인쇄" 속성을 업데이트하려면 어떻게 해야 하나요?

 PDF에서 "마지막으로 인쇄됨" 속성을 설정하여 업데이트할 수 있습니다.`setUpdateLastPrintedProperty` 에게`true` ~에`PdfSaveOptions`이는 PDF 메타데이터의 마지막 인쇄 날짜를 반영합니다.

### PDF로 변환할 때 이미지 품질을 어떻게 향상시킬 수 있나요?

 이미지 품질을 개선하려면 이미지 보간을 설정하여 활성화하세요.`setInterpolateImages` 에게`true` ~에`PdfSaveOptions`이렇게 하면 PDF에서 더 부드럽고 더 높은 품질의 이미지가 생성됩니다.