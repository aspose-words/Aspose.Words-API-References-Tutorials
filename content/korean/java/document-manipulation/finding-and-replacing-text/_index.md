---
title: Aspose.Words for Java에서 텍스트 찾기 및 바꾸기
linktitle: 텍스트 찾기 및 바꾸기
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 Word 문서에서 텍스트를 찾고 바꾸는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다. Java 문서 조작 기술을 향상시키십시오.
type: docs
weight: 15
url: /ko/java/document-manipulation/finding-and-replacing-text/
---

## Aspose.Words for Java에서 텍스트 찾기 및 바꾸기 소개

Aspose.Words for Java는 Word 문서를 프로그래밍 방식으로 작업할 수 있는 강력한 Java API입니다. Word 문서를 다룰 때 일반적인 작업 중 하나는 텍스트를 찾고 바꾸는 것입니다. 템플릿의 자리 표시자를 업데이트해야 하거나 더 복잡한 텍스트 조작을 수행해야 하는 경우 Aspose.Words for Java는 목표를 효율적으로 달성하는 데 도움이 될 수 있습니다.

## 전제조건

텍스트 찾기 및 바꾸기에 대해 자세히 알아보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 자바 개발 환경
- Aspose.Words for Java 라이브러리
- 작업할 샘플 Word 문서

 Aspose.Words for Java 라이브러리는 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/java/).

## 간단한 텍스트 찾기 및 바꾸기

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// DocumentBuilder 만들기
DocumentBuilder builder = new DocumentBuilder(doc);

// 텍스트 찾기 및 바꾸기
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

 이 예에서는 Word 문서를 로드하고`DocumentBuilder` , 그리고`replace` 문서 내에서 "이전 텍스트"를 찾아 "새 텍스트"로 바꾸는 방법입니다.

## 정규식 사용

정규식은 텍스트 검색 및 바꾸기를 위한 강력한 패턴 일치 기능을 제공합니다. Aspose.Words for Java는 고급 찾기 및 바꾸기 작업을 위한 정규식을 지원합니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// DocumentBuilder 만들기
DocumentBuilder builder = new DocumentBuilder(doc);

// 정규식을 사용하여 텍스트 찾기 및 바꾸기
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이 예에서는 정규식 패턴을 사용하여 문서 내의 텍스트를 찾고 바꿉니다.

## 필드 내부의 텍스트 무시

찾기 및 바꾸기 작업을 수행할 때 필드 내부의 텍스트를 무시하도록 Aspose.Words를 구성할 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// FindReplaceOptions 인스턴스를 생성하고 IgnoreFields를 true로 설정합니다.
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// 텍스트를 바꿀 때 옵션 사용
doc.getRange().replace("text-to-replace", "new-text", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이는 병합 필드와 같은 필드 내부의 텍스트가 바뀌지 않도록 제외하려는 경우에 유용합니다.

## 삭제 개정 내 텍스트 무시

찾기 및 바꾸기 작업 중에 삭제 개정 내의 텍스트를 무시하도록 Aspose.Words를 구성할 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// FindReplaceOptions 인스턴스를 생성하고 IgnoreDeleted를 true로 설정합니다.
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// 텍스트를 바꿀 때 옵션 사용
doc.getRange().replace("text-to-replace", "new-text", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이를 통해 추적된 변경 사항에서 삭제 표시된 텍스트를 교체되지 않도록 제외할 수 있습니다.

## 삽입 개정 내 텍스트 무시

찾기 및 바꾸기 작업 중에 삽입 개정 안의 텍스트를 무시하도록 Aspose.Words를 구성할 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// FindReplaceOptions 인스턴스를 생성하고 IgnoreInserted를 true로 설정합니다.
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// 텍스트를 바꿀 때 옵션 사용
doc.getRange().replace("text-to-replace", "new-text", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이를 통해 추적된 변경 내용에 삽입된 것으로 표시된 텍스트가 바뀌지 않도록 제외할 수 있습니다.

## 텍스트를 HTML로 바꾸기

Aspose.Words for Java를 사용하여 텍스트를 HTML 콘텐츠로 바꿀 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// 사용자 정의 교체 콜백을 사용하여 FindReplaceOptions 인스턴스 생성
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// 텍스트를 바꿀 때 옵션 사용
doc.getRange().replace("text-to-replace", "new-html-content", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

 이 예에서는 사용자 정의를 사용합니다.`ReplaceWithHtmlEvaluator` 텍스트를 HTML 콘텐츠로 대체합니다.

## 머리글과 바닥글의 텍스트 바꾸기

Word 문서의 머리글과 바닥글 내에서 텍스트를 찾고 바꿀 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// 머리글 및 바닥글 컬렉션 가져오기
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// 텍스트를 바꾸려는 머리글 또는 바닥글 유형을 선택합니다(예: HeaderFooterType.FOOTER_PRIMARY).
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// FindReplaceOptions 인스턴스를 생성하고 바닥글 범위에 적용합니다.
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이를 통해 머리글과 바닥글에서 텍스트 교체를 구체적으로 수행할 수 있습니다.

## 머리글 및 바닥글 순서에 대한 변경 사항 표시

Aspose.Words를 사용하여 문서의 머리글 및 바닥글 순서에 대한 변경 사항을 표시할 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// 첫 번째 섹션 가져오기
Section firstPageSection = doc.getFirstSection();

// FindReplaceOptions 인스턴스를 생성하고 문서 범위에 적용합니다.
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//머리글 및 바닥글 순서에 영향을 미치는 텍스트 바꾸기
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이를 통해 문서의 머리글 및 바닥글 순서와 관련된 변경 사항을 시각화할 수 있습니다.

## 텍스트를 필드로 바꾸기

Aspose.Words for Java를 사용하여 텍스트를 필드로 바꿀 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// FindReplaceOptions 인스턴스를 생성하고 필드에 대한 사용자 지정 대체 콜백을 설정합니다.
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// 텍스트를 바꿀 때 옵션 사용
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

 이 예에서는 텍스트를 필드로 바꾸고 필드 유형을 지정합니다(예:`FieldType.FIELD_MERGE_FIELD`).

## 평가자로 교체

사용자 정의 평가기를 사용하여 대체 텍스트를 동적으로 결정할 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// FindReplaceOptions 인스턴스를 생성하고 사용자 지정 대체 콜백을 설정합니다.
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// 텍스트를 바꿀 때 옵션 사용
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이 예에서는 사용자 정의 평가기(`MyReplaceEvaluator`) 텍스트를 교체합니다.

## 정규식으로 바꾸기

Aspose.Words for Java를 사용하면 정규식을 사용하여 텍스트를 바꿀 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// 정규식을 사용하여 텍스트 찾기 및 바꾸기
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이 예에서는 정규식 패턴을 사용하여 문서 내의 텍스트를 찾고 바꿉니다.

## 대체 패턴 내에서 인식 및 대체

Aspose.Words for Java를 사용하여 대체 패턴 내에서 대체를 인식하고 만들 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

//UseSubstitutions를 true로 설정하여 FindReplaceOptions 인스턴스를 생성합니다.
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// 텍스트를 패턴으로 바꿀 때 옵션 사용
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이를 통해 고급 교체를 위해 교체 패턴 내에서 교체를 수행할 수 있습니다.

## 문자열로 바꾸기

Aspose.Words for Java를 사용하여 텍스트를 간단한 문자열로 바꿀 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// 텍스트를 문자열로 바꾸기
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이 예에서는 문서 내에서 "교체할 텍스트"를 "새 문자열"로 바꿉니다.

## 기존 주문 사용

찾기 및 바꾸기 작업을 수행할 때 레거시 순서를 사용할 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// FindReplaceOptions 인스턴스를 생성하고 UseLegacyOrder를 true로 설정합니다.
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// 텍스트를 바꿀 때 옵션 사용
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이를 통해 찾기 및 바꾸기 작업에 레거시 순서를 사용할 수 있습니다.

## 테이블의 텍스트 바꾸기

Word 문서의 표 내에서 텍스트를 찾고 바꿀 수 있습니다.

```java
// 문서를 로드하세요
Document doc = new Document("your-document.docx");

// 특정 테이블 가져오기(예: 첫 번째 테이블)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// 테이블의 텍스트를 바꾸려면 FindReplaceOptions를 사용하세요.
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// 수정된 문서를 저장하세요
doc.save("modified-document.docx");
```

이를 통해 특히 테이블 내에서 텍스트 교체를 수행할 수 있습니다.

## 결론

Aspose.Words for Java는 Word 문서 내에서 텍스트를 찾고 바꾸는 포괄적인 기능을 제공합니다. 간단한 텍스트 교체를 수행해야 하거나 정규식, 필드 조작 또는 사용자 정의 평가기를 사용하여 고급 작업을 수행해야 하는 경우 Aspose.Words for Java가 해결해 드립니다. 이 강력한 Java 라이브러리의 잠재력을 최대한 활용하려면 Aspose에서 제공하는 광범위한 문서와 예제를 살펴보세요.

## FAQ

### Java용 Aspose.Words를 어떻게 다운로드하나요?

 Aspose.Words for Java를 웹사이트에서 다운로드할 수 있습니다.[이 링크](https://releases.aspose.com/words/java/).

### 텍스트 교체에 정규식을 사용할 수 있나요?

예, Aspose.Words for Java에서 텍스트 교체를 위해 정규식을 사용할 수 있습니다. 이를 통해 보다 진보되고 유연한 찾기 및 바꾸기 작업을 수행할 수 있습니다.

### 교체하는 동안 필드 내부의 텍스트를 어떻게 무시할 수 있나요?

 교체하는 동안 필드 내부의 텍스트를 무시하려면`IgnoreFields` 의 재산`FindReplaceOptions` 에게`true`이렇게 하면 병합 필드와 같은 필드 내의 텍스트가 대체에서 제외됩니다.

### 머리글과 바닥글 안의 텍스트를 바꿀 수 있나요?

 예, Word 문서의 머리글과 바닥글 내부의 텍스트를 바꿀 수 있습니다. 적절한 머리글이나 바닥글에 액세스하고`replace` 원하는 방식으로`FindReplaceOptions`.

### UseLegacyOrder 옵션은 무엇입니까?

 그만큼`UseLegacyOrder` 옵션`FindReplaceOptions` 찾기 및 바꾸기 작업을 수행할 때 레거시 순서를 사용할 수 있습니다. 이는 레거시 주문 동작이 필요한 특정 시나리오에서 유용할 수 있습니다.