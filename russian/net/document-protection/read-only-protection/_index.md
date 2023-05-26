---
title: Защита только для чтения
linktitle: Защита только для чтения
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как защитить документы Word, доступные только для чтения, с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-protection/read-only-protection/
---
В этом руководстве мы покажем вам, как использовать функцию защиты только для чтения Aspose.Words для .NET. Эта функция позволяет сделать документ Word доступным только для чтения, чтобы предотвратить несанкционированное изменение. Выполните следующие действия:

## Шаг 1: Создание документа и применение защиты

Начните с создания экземпляра класса Document и объекта DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Запишите содержимое в документ
Используйте объект DocumentBuilder для записи содержимого в документ:

```csharp
builder.Write("Open document as read-only");
```

## Шаг 3. Установите пароль и сделайте документ доступным только для чтения

Задайте пароль для документа с помощью свойства SetPassword() объекта WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Обязательно замените «MyPassword» фактическим паролем, который вы хотите использовать.

## Шаг 4. Примените документ только для чтения

Сделайте документ доступным только для чтения, установив для свойства ReadOnlyRecommended значение true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Шаг 5. Примените защиту только для чтения и сохраните документ.

Наконец, примените защиту только для чтения, используя метод Protect() объекта Document:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Обязательно укажите правильный путь и имя файла для сохранения защищенного документа.

### Пример исходного кода для защиты только для чтения с использованием Aspose.Words для .NET

Вот полный исходный код для защиты только для чтения с использованием Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// Введите пароль длиной до 15 символов.
	doc.WriteProtection.SetPassword("MyPassword");

	// Сделайте документ доступным только для чтения.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// Применить защиту от записи как доступную только для чтения.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Следуя этим шагам, вы легко защитите свои документы

