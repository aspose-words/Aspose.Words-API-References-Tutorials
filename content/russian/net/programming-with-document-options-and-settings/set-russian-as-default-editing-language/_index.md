---
title: Установить русский язык редактирования по умолчанию
linktitle: Установить русский язык редактирования по умолчанию
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по установке русского языка в качестве языка редактирования документа по умолчанию с помощью Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

В этом уроке мы познакомим вас с исходным кодом C#, чтобы установить русский язык в качестве языка редактирования по умолчанию с помощью Aspose.Words для .NET. Эта функция позволяет вам установить язык по умолчанию при загрузке документа.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ Word, для которого хотим установить русский язык в качестве языка редактирования по умолчанию. Используйте следующий код для загрузки документа:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Проверка языка по умолчанию

После загрузки документа мы проверим, правильно ли установлен русский язык по умолчанию. Используйте следующий код, чтобы получить идентификатор языка по умолчанию:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Код проверяет, соответствует ли идентификатор языка русскому. По результату выдает соответствующее сообщение.

### Пример исходного кода для установки русского языка в качестве языка редактирования по умолчанию с использованием Aspose.Words для .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Обязательно укажите правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как установить русский язык в качестве языка редактирования документа по умолчанию с помощью Aspose.Words для .NET. Следуя пошаговому руководству