---
title: Удалить ограничение только для чтения
linktitle: Удалить ограничение только для чтения
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как снять ограничение только для чтения из документа Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-protection/remove-read-only-restriction/
---
В этом руководстве мы покажем вам, как использовать Aspose.Words для функции снятия ограничений только для чтения .NET. Эта функция позволяет снять ограничение «только для чтения» с документа Word, чтобы сделать его редактируемым. Выполните следующие действия:

## Шаг 1: Создание документа и установка защиты

Начните с создания экземпляра класса Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Задайте пароль для документа с помощью свойства SetPassword() объекта WriteProtection:

Обязательно замените «MyPassword» фактическим паролем, который вы использовали для защиты документа.

## Шаг 2. Снимите ограничение только для чтения

Чтобы снять ограничение только для чтения, задайте для свойства ReadOnlyRecommended значение false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Шаг 3. Примените неограниченную защиту

Наконец, примените неограниченную защиту, используя метод Protect() объекта Document:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Обязательно укажите правильный путь и имя файла, чтобы сохранить документ без ограничения только для чтения.

### Пример исходного кода для удаления ограничения только для чтения с использованием Aspose.Words для .NET

Вот полный исходный код для снятия ограничения только для чтения с использованием Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// Введите пароль длиной до 15 символов.
	doc.WriteProtection.SetPassword("MyPassword");

	// Удалите параметр только для чтения.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// Применить защиту от записи без какой-либо защиты.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

Следуя этим шагам, вы можете легко удалить ограничение только для чтения из документа Word с помощью Aspose.Words для .NET.

