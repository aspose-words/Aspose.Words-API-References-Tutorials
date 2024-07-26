---
title: Aspose.Words for Java에서 정리 옵션 사용
linktitle: 정리 옵션 사용
second_title: Aspose.Words Java 문서 처리 API
description: Java 정리 옵션용 Aspose.Words를 사용하여 문서 명확성을 향상하세요. 빈 단락, 사용하지 않는 영역 등을 제거하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/java/document-manipulation/using-cleanup-options/
---

## Aspose.Words for Java에서 정리 옵션 사용 소개

이 튜토리얼에서는 편지 병합 프로세스 중에 문서를 조작하고 정리하기 위해 Aspose.Words for Java의 정리 옵션을 사용하는 방법을 살펴보겠습니다. 정리 옵션을 사용하면 빈 단락, 사용하지 않는 영역 제거 등 문서 정리의 다양한 측면을 제어할 수 있습니다.

## 전제조건

 시작하기 전에 Aspose.Words for Java 라이브러리가 프로젝트에 통합되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/java/).

## 1단계: 빈 단락 제거

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 병합 필드 삽입
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// 정리 옵션 설정
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// 문장 부호가 있는 단락 정리 활성화
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// 메일 병합 실행
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// 문서 저장
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

이 예에서는 새 문서를 만들고, 병합 필드를 삽입하고, 빈 단락을 제거하도록 정리 옵션을 설정합니다. 또한 구두점이 있는 단락을 제거할 수도 있습니다. 편지 병합을 실행한 후 문서는 지정된 정리가 적용된 상태로 저장됩니다.

## 2단계: 병합되지 않은 영역 제거

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// 사용하지 않는 영역을 제거하는 정리 옵션 설정
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// 지역과 메일 병합 실행
doc.getMailMerge().executeWithRegions(data);

// 문서 저장
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

이 예에서는 병합 영역이 있는 기존 문서를 열고, 사용되지 않는 영역을 제거하도록 정리 옵션을 설정한 다음, 빈 데이터로 메일 병합을 실행합니다. 이 프로세스는 문서에서 사용되지 않은 영역을 자동으로 제거합니다.

## 3단계: 빈 필드 제거

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// 빈 필드를 제거하는 정리 옵션 설정
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// 메일 병합 실행
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// 문서 저장
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

이 예에서는 병합 필드가 있는 문서를 열고, 빈 필드를 제거하도록 정리 옵션을 설정하고, 데이터와 함께 메일 병합을 실행합니다. 병합 후 빈 필드는 문서에서 제거됩니다.

## 4단계: 사용되지 않는 필드 제거

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// 사용하지 않는 필드를 제거하기 위한 정리 옵션 설정
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// 메일 병합 실행
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// 문서 저장
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

이 예에서는 병합 필드가 있는 문서를 열고, 사용하지 않는 필드를 제거하도록 정리 옵션을 설정하고, 데이터와 함께 메일 병합을 실행합니다. 병합 후 사용되지 않은 필드는 문서에서 제거됩니다.

## 5단계: 포함 필드 제거

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// 포함된 필드를 제거하도록 정리 옵션 설정
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// 메일 병합 실행
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// 문서 저장
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

이 예에서는 병합 필드가 있는 문서를 열고, 포함된 필드를 제거하도록 정리 옵션을 설정하고, 데이터와 함께 메일 병합을 실행합니다. 병합 후에는 필드 자체가 문서에서 제거됩니다.

## 6단계: 빈 테이블 행 제거

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// 빈 테이블 행을 제거하는 정리 옵션 설정
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// 메일 병합 실행
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// 문서 저장
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

이 예에서는 테이블과 병합 필드가 있는 문서를 열고, 빈 테이블 행을 제거하도록 정리 옵션을 설정하고, 데이터와 함께 메일 병합을 실행합니다. 병합 후에는 빈 테이블 행이 문서에서 제거됩니다.

## 결론

이 튜토리얼에서는 편지 병합 프로세스 중에 문서를 조작하고 정리하기 위해 Aspose.Words for Java의 정리 옵션을 사용하는 방법을 배웠습니다. 이러한 옵션은 문서 정리에 대한 세밀한 제어를 제공하므로 세련되고 사용자 정의된 문서를 쉽게 만들 수 있습니다.

## FAQ

### Aspose.Words for Java의 정리 옵션은 무엇입니까?

Aspose.Words for Java의 정리 옵션은 메일 병합 프로세스 중 문서 정리의 다양한 측면을 제어할 수 있는 설정입니다. 이를 통해 빈 단락, 사용하지 않는 영역 등과 같은 불필요한 요소를 제거하여 최종 문서를 잘 구성하고 세련되게 만들 수 있습니다.

### 내 문서에서 빈 단락을 제거하려면 어떻게 해야 합니까?

 Aspose.Words for Java를 사용하여 문서에서 빈 단락을 제거하려면`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` 옵션을 true로 설정합니다. 이렇게 하면 내용이 없는 단락이 자동으로 제거되어 문서가 더 깔끔해집니다.

###  의 목적은 무엇입니까?`REMOVE_UNUSED_REGIONS` cleanup option?

 그만큼`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` 옵션은 편지 병합 프로세스 중에 해당 데이터가 없는 문서의 영역을 제거하는 데 사용됩니다. 사용하지 않는 자리 표시자를 제거하여 문서를 깔끔하게 유지하는 데 도움이 됩니다.

### Aspose.Words for Java를 사용하여 문서에서 빈 테이블 행을 제거할 수 있나요?

 예, 다음을 설정하여 문서에서 빈 테이블 행을 제거할 수 있습니다.`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`정리 옵션을 true로 설정합니다. 이렇게 하면 데이터가 포함되지 않은 표 행이 자동으로 삭제되어 문서에 표가 잘 구조화되도록 합니다.

###  설정하면 어떻게 되나요?`REMOVE_CONTAINING_FIELDS` option?

 설정`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` 옵션은 메일 병합 프로세스 중에 포함된 단락을 포함하여 전체 병합 필드를 문서에서 제거합니다. 이는 병합 필드와 관련 텍스트를 제거하려는 경우에 유용합니다.

### 내 문서에서 사용하지 않는 병합 필드를 제거하려면 어떻게 해야 합니까?

 문서에서 사용하지 않는 병합 필드를 제거하려면 다음을 설정할 수 있습니다.`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` 옵션을 true로 설정합니다. 이렇게 하면 메일 병합 중에 채워지지 않은 병합 필드가 자동으로 제거되어 문서가 더 깔끔해집니다.

###  차이점은 무엇 입니까?`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 그만큼`REMOVE_EMPTY_FIELDS` 옵션은 메일 병합 프로세스 중에 데이터가 없거나 비어 있는 병합 필드를 제거합니다. 반면,`REMOVE_UNUSED_FIELDS`옵션은 병합 중에 데이터로 채워지지 않은 병합 필드를 제거합니다. 이들 사이의 선택은 내용이 없는 필드를 제거할지 또는 특정 병합 작업에서 사용되지 않는 필드를 제거할지에 따라 달라집니다.

### 구두점이 있는 단락을 제거하려면 어떻게 해야 합니까?

 문장 부호가 있는 단락을 제거하려면`cleanupParagraphsWithPunctuationMarks` 옵션을 true로 설정하고 정리할 문장 부호를 지정합니다. 이를 통해 불필요한 문장부호만 삭제하여 더욱 세련된 문서를 만들 수 있습니다.

### Aspose.Words for Java에서 정리 옵션을 사용자 정의할 수 있나요?

예, 특정 요구 사항에 따라 정리 옵션을 사용자 정의할 수 있습니다. 적용할 정리 옵션을 선택하고 문서 정리 요구 사항에 따라 이를 구성하여 최종 문서가 원하는 표준을 충족하는지 확인할 수 있습니다.