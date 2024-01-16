---
title: Aspose.Words for Java에서 문서를 ODT 형식으로 저장하기
linktitle: ODT 형식으로 문서 저장
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 문서를 ODT 형식으로 저장하는 방법을 알아보세요. 오픈 소스 오피스 제품군과의 호환성을 보장합니다.
type: docs
weight: 19
url: /ko/java/document-loading-and-saving/saving-documents-as-odt-format/
---

## Aspose.Words for Java에서 문서를 ODT 형식으로 저장하는 방법 소개

이 기사에서는 Aspose.Words for Java를 사용하여 문서를 ODT(Open Document Text) 형식으로 저장하는 방법을 살펴보겠습니다. ODT는 OpenOffice 및 LibreOffice를 포함한 다양한 Office 제품군에서 사용되는 널리 사용되는 개방형 표준 문서 형식입니다. 문서를 ODT 형식으로 저장하면 이러한 소프트웨어 패키지와의 호환성을 보장할 수 있습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Java 개발 환경: 시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오.

2.  Aspose.Words for Java: Aspose.Words for Java 라이브러리를 다운로드하고 설치하세요. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/words/java/).

3. 샘플 문서: ODT 형식으로 변환하려는 샘플 Word 문서(예: "Document.docx")가 있습니다.

## 1단계: 문서 로드

먼저 Aspose.Words for Java를 사용하여 Word 문서를 로드해 보겠습니다.

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
```

 여기,`"Your Directory Path"` 문서가 있는 디렉토리를 가리켜야 합니다.

## 2단계: ODT 저장 옵션 지정

문서를 ODT로 저장하려면 ODT 저장 옵션을 지정해야 합니다. 또한 문서의 측정 단위를 설정할 수 있습니다. Open Office는 센티미터를 사용하고 MS Office는 인치를 사용합니다. 인치로 설정하겠습니다.

```java
OdtSaveOptions saveOptions = new OdtSaveOptions();
saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES);
```

## 3단계: 문서 저장

이제 문서를 ODT 형식으로 저장할 차례입니다.

```java
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

 여기,`"Your Directory Path"` 변환된 ODT 파일을 저장하려는 디렉터리를 가리켜야 합니다.

## Aspose.Words for Java에서 문서를 ODT 형식으로 저장하기 위한 완전한 소스 코드

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
// Open Office는 길이, 너비 및 기타 측정 가능한 형식을 지정할 때 센티미터를 사용합니다.
// 문서의 콘텐츠 속성과 MS Office는 인치를 사용합니다.
OdtSaveOptions saveOptions = new OdtSaveOptions(); { saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES); }
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## 결론

이 기사에서는 Aspose.Words for Java를 사용하여 문서를 ODT 형식으로 저장하는 방법을 배웠습니다. 이는 OpenOffice 및 LibreOffice와 같은 오픈 소스 오피스 제품군과의 호환성을 보장해야 할 때 특히 유용할 수 있습니다.

## FAQ

### Java용 Aspose.Words를 어떻게 다운로드할 수 있나요?

 Aspose 웹사이트에서 Java용 Aspose.Words를 다운로드할 수 있습니다. 방문하다[이 링크](https://releases.aspose.com/words/java/)다운로드 페이지에 접속하려면

### 문서를 ODT 형식으로 저장하면 어떤 이점이 있나요?

문서를 ODT 형식으로 저장하면 OpenOffice 및 LibreOffice와 같은 오픈 소스 오피스 제품군과의 호환성이 보장되므로 이러한 소프트웨어 패키지 사용자가 문서에 더 쉽게 액세스하고 편집할 수 있습니다.

### ODT 형식으로 저장할 때 측정 단위를 지정해야 합니까?

예, 측정 단위를 지정하는 것이 좋습니다. Open Office는 기본적으로 센티미터를 사용하므로 인치로 설정하면 일관된 형식이 보장됩니다.

### 일괄 처리로 여러 문서를 ODT 형식으로 변환할 수 있습니까?

예, Aspose.Words for Java를 사용하면 문서 파일을 반복하고 변환 프로세스를 적용하여 여러 문서를 ODT 형식으로 자동 변환할 수 있습니다.

### Aspose.Words for Java는 최신 Java 버전과 호환됩니까?

Aspose.Words for Java는 최신 Java 버전을 지원하도록 정기적으로 업데이트되어 호환성과 성능 향상을 보장합니다. 최신 정보는 설명서의 시스템 요구 사항을 확인하세요.