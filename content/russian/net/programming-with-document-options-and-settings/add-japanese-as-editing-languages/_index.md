---
title: Добавить японский в качестве языков редактирования
linktitle: Добавить японский в качестве языков редактирования
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по добавлению японского языка в качестве языка редактирования с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

В этом уроке мы шаг за шагом покажем вам, как понять и реализовать функциональность добавления японского языка в качестве языка редактирования с помощью Aspose.Words для .NET. Эта функция позволяет вам устанавливать языковые настройки при загрузке документа и добавлять японский язык в качестве языка редактирования.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ Word, который не содержит языка редактирования по умолчанию и в который мы хотим добавить японский язык. Используйте следующий код для загрузки документа:

```csharp
LoadOptions loadOptions = new LoadOptions();

// Установите языковые настройки, которые будут использоваться при загрузке документа.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Шаг 3. Проверка языка по умолчанию

После загрузки документа мы проверим, правильно ли установлен японский язык редактирования по умолчанию. Используйте следующий код, чтобы получить идентификатор дальневосточного языка:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Код проверяет, соответствует ли идентификатор дальневосточного языка идентификатору японского языка. По результату выдает соответствующее сообщение.

### Пример исходного кода для добавления японского языка в качестве языков редактирования с использованием Aspose.Words для .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Установите языковые настройки, которые будут использоваться при загрузке документа.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

