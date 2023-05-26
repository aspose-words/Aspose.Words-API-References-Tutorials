---
title: Снять защиту документа
linktitle: Снять защиту документа
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как снять защиту с документа Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-protection/remove-document-protection/
---

В этом руководстве мы покажем вам, как использовать функцию снятия защиты документа в Aspose.Words для .NET. Эта функция позволяет снять защиту с документа Word, чтобы сделать его доступным для дальнейшего редактирования. Выполните следующие действия:

## Шаг 1: Создание документа и добавление содержимого

Начните с создания экземпляра класса Document и объекта DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Добавьте содержимое в документ

Используйте объект DocumentBuilder, чтобы добавить содержимое в документ:

```csharp
builder.Writeln("Text added to a document.");
```

## Шаг 3. Снимите защиту с документа

Чтобы снять защиту с документа, вы можете использовать метод Unprotect() объекта Document. Вы можете снять защиту без пароля или с правильным паролем. Снятие беспарольной защиты:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Обязательно замените «newPassword» правильным паролем документа.

## Шаг 4. Сохраните документ без защиты

Наконец, сохраните документ незащищенным, используя метод Save() объекта Document:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Обязательно укажите правильный путь и имя файла, чтобы сохранить документ незащищенным.

### Пример исходного кода для удаления защиты документов с помощью Aspose.Words для .NET

Вот полный исходный код для снятия защиты документа с помощью Aspose.Words for .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Text added to a document.");

	// Защита документов может быть снята либо без пароля, либо с правильным паролем.
	doc.Unprotect();
	doc.Protect(ProtectionType.ReadOnly, "newPassword");
	doc.Unprotect("newPassword");

	doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Следуя этим шагам, вы можете легко снять защиту с документа Word с помощью Aspose.Words для .NET.
