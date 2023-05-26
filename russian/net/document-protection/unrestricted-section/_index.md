---
title: Неограниченный раздел
linktitle: Неограниченный раздел
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как определить неограниченные разделы в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-protection/unrestricted-section/
---

В этом руководстве мы покажем вам, как использовать функцию неограниченного раздела Aspose.Words для .NET. Эта функция позволяет определить определенные разделы в документе Word, которые не защищены, даже если остальная часть документа защищена. Выполните следующие действия:

## Шаг 1: Создание документа и разделов

Начните с создания экземпляра класса Document и объекта DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Добавьте содержимое в документ
Используйте объект DocumentBuilder, чтобы добавить содержимое в документ и вставить разрывы разделов:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Шаг 3: Защитите документ и разделы

Защита раздела работает только при включенной защите документа и разрешено только редактирование полей формы. Вы можете защитить документ, используя метод Protect() объекта Document:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Обязательно укажите правильный тип защиты и установите нужный пароль.

## Шаг 4: Отключение защиты для определенного раздела

По умолчанию защищены все разделы, но вы можете выборочно отключить защиту для определенного раздела с помощью свойства ProtectedForForms объекта Section:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

В данном примере защита отключена для первого раздела.

## Шаг 5: Сохраните документ

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Обязательно укажите правильный путь и имя файла, чтобы сохранить документ с неограниченными разделами.

### Пример исходного кода для неограниченного раздела с использованием Aspose.Words для .NET

Вот полный исходный код неограниченного раздела с использованием Aspose.Words для .NET:


```csharp

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Вставьте два раздела с текстом.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Защита раздела работает только при включенной защите документа и разрешено только редактирование полей формы.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// По умолчанию все разделы защищены, но мы можем выборочно отключить защиту.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Выполнив эти шаги, вы сможете легко определить неограниченные разделы в документе Word с помощью Aspose.Words для .NET.

