---
title: Сохранение документов в формате OOXML в Aspose.Words для Java
linktitle: Сохранение документов в формате OOXML
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как сохранять документы в формате OOXML с помощью Aspose.Words для Java. Без труда защитите, оптимизируйте и настройте свои файлы.
type: docs
weight: 20
url: /ru/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Введение в сохранение документов в формате OOXML в Aspose.Words для Java

В этом руководстве мы рассмотрим, как сохранять документы в формате OOXML с помощью Aspose.Words для Java. OOXML (Office Open XML) — это формат файлов, используемый Microsoft Word и другими офисными приложениями. Мы рассмотрим различные варианты и настройки сохранения документов в формате OOXML.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что в вашем проекте установлена библиотека Aspose.Words for Java.

## Сохранение документа с шифрованием пароля

Вы можете зашифровать свой документ паролем, сохраняя его в формате OOXML. Вот как вы можете это сделать:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Загрузите документ
Document doc = new Document("Document.docx");

// Создайте OoxmlSaveOptions и установите пароль.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Сохраните документ с шифрованием
doc.save("EncryptedDoc.docx", saveOptions);
```

## Настройка соответствия OOXML

Вы можете указать уровень соответствия OOXML при сохранении документа. Например, вы можете установить ISO 29500:2008 (строгий). Вот как:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Загрузите документ
Document doc = new Document("Document.docx");

// Оптимизировать для Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// Создайте OoxmlSaveOptions и установите уровень соответствия.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Сохраните документ с настройкой соответствия
doc.save("ComplianceDoc.docx", saveOptions);
```

## Обновить свойство времени последнего сохранения

Вы можете обновить свойство «Время последнего сохранения» документа при его сохранении. Вот как:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Загрузите документ
Document doc = new Document("Document.docx");

// Создайте OoxmlSaveOptions и включите обновление свойства «Время последнего сохранения».
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Сохраните документ с обновленным свойством.
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Сохранение устаревших управляющих персонажей

Если ваш документ содержит устаревшие управляющие символы, вы можете сохранить их при сохранении. Вот как:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// Загрузите документ с устаревшими управляющими символами
Document doc = new Document("LegacyControlChars.doc");

//Создайте OoxmlSaveOptions в формате FLAT_OPC и включите сохранение устаревших управляющих символов.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// Сохраните документ с устаревшими управляющими символами.
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Настройка уровня сжатия

Вы можете настроить уровень сжатия при сохранении документа. Например, вы можете установить значение SUPER_FAST для минимального сжатия. Вот как:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Загрузите документ
Document doc = new Document("Document.docx");

// Создайте OoxmlSaveOptions и установите уровень сжатия.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Сохраните документ с указанным уровнем сжатия.
doc.save("FastCompressionDoc.docx", saveOptions);
```

Это некоторые ключевые параметры и настройки, которые вы можете использовать при сохранении документов в формате OOXML с помощью Aspose.Words для Java. Не стесняйтесь изучить дополнительные параметры и настроить процесс сохранения документов по мере необходимости.

## Полный исходный код для сохранения документов в формате OOXML в Aspose.Words для Java

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

## Заключение

В этом подробном руководстве мы рассмотрели, как сохранять документы в формате OOXML с помощью Aspose.Words для Java. Если вам нужно зашифровать свои документы с помощью паролей, обеспечить соответствие определенным стандартам OOXML, обновить свойства документа, сохранить устаревшие управляющие символы или настроить уровни сжатия, Aspose.Words предоставляет универсальный набор инструментов для удовлетворения ваших требований.

## Часто задаваемые вопросы

### Как снять защиту паролем с документа, защищенного паролем?

Чтобы снять защиту паролем с документа, защищенного паролем, вы можете открыть документ с правильным паролем, а затем сохранить его, не указывая пароль в параметрах сохранения. Это сохранит документ без защиты паролем.

### Могу ли я установить дополнительные свойства при сохранении документа в формате OOXML?

 Да, вы можете установить дополнительные свойства для документа перед его сохранением в формате OOXML. Использовать`BuiltInDocumentProperties` и`CustomDocumentProperties` классы для установки различных свойств, таких как автор, заголовок, ключевые слова и пользовательские свойства.

### Каков уровень сжатия по умолчанию при сохранении документа в формате OOXML?

 Уровень сжатия по умолчанию при сохранении документа в формате OOXML с использованием Aspose.Words для Java:`NORMAL` . Вы можете изменить уровень сжатия на`SUPER_FAST` или`MAXIMUM` по мере необходимости.