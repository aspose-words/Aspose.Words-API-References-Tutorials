---
title: Защита паролем
linktitle: Защита паролем
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как защитить паролем документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-protection/password-protection/
---

В этом руководстве мы покажем вам, как использовать функцию защиты паролем Aspose.Words для .NET. Эта функция позволяет защитить документ Word паролем для обеспечения его конфиденциальности. Выполните следующие действия:

## Шаг 1: Создание документа и применение защиты

Начните с создания экземпляра класса Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Шаг 2. Примените защиту паролем

Затем вы можете применить защиту паролем, используя метод Protect() объекта Document:

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

Обязательно замените «пароль» фактическим паролем, который вы хотите использовать для защиты документа.

## Шаг 3: Сохранение защищенного документа

Наконец, вы можете сохранить защищенный документ, используя метод Save() объекта Document:

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

Обязательно укажите правильный путь и имя файла для сохранения защищенного документа.

### Пример исходного кода для защиты паролем с использованием Aspose.Words для .NET

Вот полный исходный код для защиты паролем с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//Применить защиту документа.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

Не забудьте заменить «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на каталог ваших документов и «пароль» на фактический пароль, который вы хотите использовать.

