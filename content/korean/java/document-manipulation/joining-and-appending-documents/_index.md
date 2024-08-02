---
title: Aspose.Words for Java에서 문서 결합 및 추가
linktitle: 문서 결합 및 추가
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 손쉽게 문서를 결합하고 추가하는 방법을 알아보세요. 서식을 유지하고 머리글 바닥글을 관리하는 등의 작업을 수행하세요.
type: docs
weight: 30
url: /ko/java/document-manipulation/joining-and-appending-documents/
---

## Aspose.Words for Java에서 문서 결합 및 추가 소개

이 튜토리얼에서는 Aspose.Words for Java 라이브러리를 사용하여 문서를 결합하고 추가하는 방법을 살펴보겠습니다. 서식과 구조를 유지하면서 여러 문서를 원활하게 병합하는 방법을 배우게 됩니다.

## 전제 조건

시작하기 전에 Java 프로젝트에 Aspose.Words for Java API가 설정되어 있는지 확인하세요.

## 문서 결합 옵션

### 단순 추가

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### 가져오기 형식 옵션으로 추가

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### 빈 문서에 추가

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### 페이지 번호 변환으로 추가

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // NUMPAGES개 필드 변환
dstDoc.updatePageLayout(); // 올바른 번호 매기기를 위해 페이지 레이아웃 업데이트
```

## 다양한 페이지 설정 처리

페이지 설정이 다른 문서를 추가하는 경우:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// 페이지 설정 설정이 대상 문서와 일치하는지 확인
```

## 다양한 스타일의 문서 결합

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## 스마트 스타일 동작

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## DocumentBuilder를 사용하여 문서 삽입

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## 소스 번호 유지

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## 텍스트 상자 처리

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## 머리글 및 바닥글 관리

### 머리글과 바닥글 연결하기

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### 머리글 및 바닥글 연결 해제

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## 결론

Aspose.Words for Java는 형식 유지, 다양한 페이지 설정 처리, 머리글 및 바닥글 관리 등 문서 결합 및 추가를 위한 유연하고 강력한 도구를 제공합니다. 특정 문서 처리 요구 사항을 충족하려면 이러한 기술을 실험해 보세요.

## FAQ

### 다양한 스타일의 문서를 어떻게 원활하게 결합할 수 있나요?

 다양한 스타일의 문서를 결합하려면 다음을 사용하세요.`ImportFormatMode.USE_DESTINATION_STYLES` 첨부할 때.

### 문서를 추가할 때 페이지 번호 매기기를 유지할 수 있나요?

 예, 다음을 사용하여 페이지 번호 매기기를 보존할 수 있습니다.`convertNumPageFieldsToPageRef` 메소드 및 페이지 레이아웃 업데이트.

### 스마트 스타일 행동이란 무엇입니까?

 스마트 스타일 동작은 문서를 추가할 때 일관된 스타일을 유지하는 데 도움이 됩니다. 함께 사용하세요`ImportFormatOptions` 더 나은 결과를 위해.

### 문서를 추가할 때 텍스트 상자를 어떻게 처리합니까?

세트`importFormatOptions.setIgnoreTextBoxes(false)` 추가하는 동안 텍스트 상자를 포함합니다.

### 문서 간에 머리글과 바닥글을 연결/연결 해제하려면 어떻게 해야 하나요?

 머리글과 바닥글을 연결할 수 있습니다.`linkToPrevious(true)` 또는 연결을 해제하세요.`linkToPrevious(false)` 필요에 따라.