---
title: Aspose.Words for Java에서 문서를 OOXML 형식으로 저장하기
linktitle: OOXML 형식으로 문서 저장
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 문서를 OOXML 형식으로 저장하는 방법을 알아보세요. 손쉽게 파일을 보호하고, 최적화하고, 맞춤화하세요.
type: docs
weight: 20
url: /ko/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Aspose.Words for Java에서 문서를 OOXML 형식으로 저장하는 방법 소개

이 가이드에서는 Aspose.Words for Java를 사용하여 문서를 OOXML 형식으로 저장하는 방법을 살펴보겠습니다. OOXML(Office Open XML)은 Microsoft Word 및 기타 Office 응용 프로그램에서 사용되는 파일 형식입니다. OOXML 형식으로 문서를 저장하기 위한 다양한 옵션과 설정을 다룹니다.

## 전제 조건

시작하기 전에 프로젝트에 Aspose.Words for Java 라이브러리가 설정되어 있는지 확인하세요.

## 비밀번호 암호화로 문서 저장

문서를 OOXML 형식으로 저장하는 동안 비밀번호로 문서를 암호화할 수 있습니다. 방법은 다음과 같습니다.

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// 문서를 로드하세요
Document doc = new Document("Document.docx");

// OoxmlSaveOptions 생성 및 비밀번호 설정
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// 암호화하여 문서 저장
doc.save("EncryptedDoc.docx", saveOptions);
```

## OOXML 준수 설정

문서를 저장할 때 OOXML 준수 수준을 지정할 수 있습니다. 예를 들어 ISO 29500:2008(엄격)로 설정할 수 있습니다. 방법은 다음과 같습니다.

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// 문서를 로드하세요
Document doc = new Document("Document.docx");

// Word 2016에 최적화
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// OoxmlSaveOptions 생성 및 규정 준수 수준 설정
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// 규정 준수 설정으로 문서 저장
doc.save("ComplianceDoc.docx", saveOptions);
```

## 마지막으로 저장된 시간 속성 업데이트

문서를 저장할 때 문서의 "마지막 저장 시간" 속성을 업데이트하도록 선택할 수 있습니다. 방법은 다음과 같습니다.

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// 문서를 로드하세요
Document doc = new Document("Document.docx");

// OoxmlSaveOptions를 생성하고 마지막으로 저장된 시간 속성 업데이트를 활성화합니다.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// 업데이트된 속성으로 문서를 저장합니다.
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## 레거시 제어 문자 유지

문서에 레거시 제어 문자가 포함된 경우 저장하는 동안 해당 문자를 유지하도록 선택할 수 있습니다. 방법은 다음과 같습니다.

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// 레거시 제어 문자가 포함된 문서 로드
Document doc = new Document("LegacyControlChars.doc");

//FLAT_OPC 형식으로 OoxmlSaveOptions를 생성하고 레거시 제어 문자 유지를 활성화합니다.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// 레거시 제어 문자를 사용하여 문서를 저장합니다.
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## 압축 수준 설정

문서를 저장할 때 압축 수준을 조정할 수 있습니다. 예를 들어 압축을 최소화하려면 SUPER_FAST로 설정할 수 있습니다. 방법은 다음과 같습니다.

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// 문서를 로드하세요
Document doc = new Document("Document.docx");

// OoxmlSaveOptions 생성 및 압축 수준 설정
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// 지정된 압축 수준으로 문서를 저장합니다.
doc.save("FastCompressionDoc.docx", saveOptions);
```

다음은 Aspose.Words for Java를 사용하여 문서를 OOXML 형식으로 저장할 때 사용할 수 있는 주요 옵션 및 설정 중 일부입니다. 자유롭게 더 많은 옵션을 살펴보고 필요에 따라 문서 저장 프로세스를 맞춤설정하세요.

## Aspose.Words for Java에서 문서를 OOXML 형식으로 저장하기 위한 완전한 소스 코드

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## 결론

이 종합 가이드에서는 Aspose.Words for Java를 사용하여 문서를 OOXML 형식으로 저장하는 방법을 살펴보았습니다. 비밀번호로 문서를 암호화하고, 특정 OOXML 표준을 준수하는지 확인하고, 문서 속성을 업데이트하고, 레거시 제어 문자를 보존하거나, 압축 수준을 조정해야 하는 경우 Aspose.Words는 요구 사항을 충족하는 다양한 도구 세트를 제공합니다.

## FAQ

### 비밀번호로 보호된 문서에서 비밀번호 보호를 제거하려면 어떻게 해야 합니까?

비밀번호로 보호된 문서에서 비밀번호 보호를 제거하려면 올바른 비밀번호로 문서를 연 다음 저장 옵션에서 비밀번호를 지정하지 않고 저장할 수 있습니다. 그러면 비밀번호 보호 없이 문서가 저장됩니다.

### 문서를 OOXML 형식으로 저장할 때 사용자 정의 속성을 설정할 수 있나요?

 예, 문서를 OOXML 형식으로 저장하기 전에 문서의 사용자 정의 속성을 설정할 수 있습니다. 사용`BuiltInDocumentProperties`그리고`CustomDocumentProperties` 작성자, 제목, 키워드, 사용자 정의 속성 등 다양한 속성을 설정하는 클래스입니다.

### 문서를 OOXML 형식으로 저장할 때 기본 압축 수준은 무엇입니까?

 Aspose.Words for Java를 사용하여 문서를 OOXML 형식으로 저장할 때 기본 압축 수준은 다음과 같습니다.`NORMAL` . 압축 수준을 다음으로 변경할 수 있습니다.`SUPER_FAST` 또는`MAXIMUM` 필요에 따라.