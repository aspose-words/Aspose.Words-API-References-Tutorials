---
title: Aspose.Words for Java에서 고정 레이아웃으로 HTML 문서 저장
linktitle: 고정 레이아웃으로 HTML 문서 저장
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java에서 고정 레이아웃으로 HTML 문서를 저장하는 방법을 알아보세요. 매끄러운 문서 서식 지정을 위한 단계별 가이드를 따르세요.
type: docs
weight: 15
url: /ko/java/document-loading-and-saving/saving-html-documents-with-fixed-layout/
---

## Aspose.Words for Java에서 고정 레이아웃으로 HTML 문서 저장하기 소개

이 포괄적인 가이드에서는 Aspose.Words for Java를 사용하여 고정된 레이아웃으로 HTML 문서를 저장하는 과정을 안내합니다. 단계별 지침과 코드 예제를 통해 이를 원활하게 달성하는 방법을 배울 수 있습니다. 그럼 바로 시작해 볼까요!

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- Java 개발 환경 설정.
- Java 라이브러리용 Aspose.Words를 설치하고 구성했습니다.

## 1단계: 문서 로딩

먼저, HTML 형식으로 저장하려는 문서를 로드해야 합니다. 방법은 다음과 같습니다.

```java
Document doc = new Document("Your Directory Path" + "YourDocument.docx");
```

 바꾸다`"YourDocument.docx"` Word 문서로의 경로를 포함합니다.

## 2단계: HTML 고정 저장 옵션 구성

 고정된 레이아웃으로 문서를 저장하려면 다음을 구성해야 합니다.`HtmlFixedSaveOptions` 클래스. 우리는 설정할 것입니다`useTargetMachineFonts`재산에`true` HTML 출력에 대상 컴퓨터의 글꼴이 사용되는지 확인하려면:

```java
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions();
saveOptions.setUseTargetMachineFonts(true);
```

## 3단계: 문서를 HTML로 저장

이제 이전에 구성한 옵션을 사용하여 고정된 레이아웃의 HTML로 문서를 저장해 보겠습니다.

```java
doc.save("Your Directory Path" + "FixedLayoutDocument.html", saveOptions);
```

 바꾸다`"FixedLayoutDocument.html"` HTML 파일에 원하는 이름을 입력하세요.

## Aspose.Words for Java에서 고정 레이아웃으로 HTML 문서를 저장하기 위한 완전한 소스 코드

```java
        Document doc = new Document("Your Directory Path" + "Bullet points with alternative font.docx");
        HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions();
        {
            saveOptions.setUseTargetMachineFonts(true);
        }
        doc.save("Your Directory Path" + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
    }
```

## 결론

이 튜토리얼에서는 Aspose.Words for Java를 사용하여 고정된 레이아웃으로 HTML 문서를 저장하는 방법을 알아보았습니다. 이러한 간단한 단계를 따르면 다양한 플랫폼에서 문서가 일관된 시각적 구조를 유지하도록 할 수 있습니다.

## 자주 묻는 질문

### 내 프로젝트에 Java용 Aspose.Words를 어떻게 설정할 수 있나요?

 Aspose.Words for Java 설정은 간단합니다. 라이브러리는 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/java/) 설명서에 제공된 설치 지침을 따르세요.[여기](https://reference.aspose.com/words/java/).

### Aspose.Words for Java를 사용하는 데 라이선스 요구 사항이 있습니까?

네, Aspose.Words for Java는 프로덕션 환경에서 사용하려면 유효한 라이선스가 필요합니다. Aspose 웹사이트에서 라이선스를 얻을 수 있습니다. 자세한 내용은 설명서에서 확인할 수 있습니다.

### HTML 출력을 더욱 세부적으로 사용자 정의할 수 있나요?

물론입니다! Aspose.Words for Java는 특정 요구 사항을 충족하도록 HTML 출력을 사용자 정의하기 위한 광범위한 옵션을 제공합니다. 사용자 정의 옵션에 대한 자세한 내용은 설명서를 탐색할 수 있습니다.

### Aspose.Words for Java는 다른 Java 버전과 호환됩니까?

네, Aspose.Words for Java는 다양한 버전의 Java와 호환됩니다. Java 개발 환경과 일치하는 Aspose.Words for Java의 호환 버전을 사용하고 있는지 확인하세요.